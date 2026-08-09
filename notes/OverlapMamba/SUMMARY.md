# OverlapMamba — Phase 1 summary

**Repo:** https://github.com/SCNU-RISLAB/OverlapMamba @ `b20add9`
**Paper:** OverlapMamba (RA-L), arXiv 2405.07966
**Hardware:** RTX 5070 Ti 16 GB (Blackwell, sm_120), driver 591.86 / CUDA 13.1, WSL2

**Bottom line:** the environment works and the model runs on Blackwell. The
authors never released the pretrained weights, so their reported numbers cannot
be reproduced.

---

## Environment

The README pins `torch==1.10.2+cu113`, which predates Blackwell and would fail
with *"no kernel image available for device"*. We ignored that pin entirely, and
it cost us nothing: **OverlapMamba does not use `mamba-ssm` or `causal-conv1d`.**
It vendors a pure-PyTorch Mamba (`mambapy/`, imported at
`modules/overlap_mamba.py:19`; the `mamba_ssm` import on line 21 is commented
out). There are no CUDA extensions to compile, so no `nvcc` is needed and any
torch with sm_120 kernels works.

What we run:

| | |
|---|---|
| Python | 3.11 (conda env `overlapmamba`) |
| torch | 2.9.1+cu128 / torchvision 0.24.1+cu128 |
| numpy | 1.26.4 |
| faiss-cpu | 1.14.3 |
| others | opencv-python-headless 4.11.0.86, scikit-learn 1.9.0, scipy 1.17.1, matplotlib 3.11.1, PyYAML 6.0.3, tensorboardX 2.6.5 |

The cu128 runtime works under the CUDA 13.1 driver via minor-version
compatibility. Verified on hardware:

```
torch 2.9.1+cu128 | NVIDIA GeForce RTX 5070 Ti | sm_120
arch_list: ['sm_70','sm_75','sm_80','sm_86','sm_90','sm_100','sm_120']
OK: sm_120 kernels execute
```

`arch_list` containing `sm_120` plus a real matmul completing — the capability
is compiled in, not merely reported.

```bash
bash repro/setup_env.sh          # conda env + torch + deps + sm_120 check
conda activate overlapmamba
```

The released eval scripts also needed six small fixes before they would run:
a broken import of a nonexistent module, an NCLT-sized hardcoded loop bound, an
`IndexError` on early queries, and three mutually inconsistent hardcoded output
directories. All are applied by `repro/apply_fixes.py` (idempotent, `--revert`
to undo) and none touch model numerics.

## Running the model — random weights

Forward pass on GPU, random init:

```
descriptor   : (2, 256)      # matches the paper's 256-D global descriptor
L2 norms     : [1. 1.]       # NetVLAD output is F.normalize'd
latency      : 6.4 ms / scan
peak VRAM    : 0.59 GB
```

VRAM is trivial, so 16 GB will not constrain batch size if we ever train.

We then generated a KITTI-shaped synthetic set (300 range images at 64×900
uint8, with a revisit structure and ground truth in the authors' format, plus a
random-init checkpoint in their `{'state_dict': ...}` layout) and ran the full
documented 3-step pipeline:

```
test_kitti00_prepare.py  ->  predicted_des_L2_dis.npz              OK
test_kitti00_topN.py     ->  recall_list.npy,  Recall@1 = 0.449    OK
test_kitti00_PR.py       ->  PR.npz, PR.png,   F1max  = 0.614      OK
```

> **These numbers are meaningless as accuracy** — random weights on synthetic
> data. They validate plumbing only. The PR curve is a degenerate straight line
> because random descriptors sit ~1e-4 apart, which is itself confirmation the
> model is untrained.

So: everything from data loading through descriptor extraction, retrieval, and
metric computation is wired up and working. The only missing piece is a trained
model.

## The pretrained weights do not exist

| Check | Result |
|---|---|
| Both README download links | **HTTP 404** |
| Full git tree, `main` and `master` | No `.pth` / `.tar` / weights of any kind |
| GitHub Releases | None |
| Git LFS | `.gitattributes` declares `*.tar filter=lfs`, but no LFS objects tracked |
| All 5 forks | Byte-identical to upstream — nobody mirrored them |

Two open issues ask for exactly this and have **zero replies**:
[#2](https://github.com/SCNU-RISLAB/OverlapMamba/issues/2) (2025-07-01) and
[#3](https://github.com/SCNU-RISLAB/OverlapMamba/issues/3) (2025-12-01). The
repo has been untouched since 2024-05-21.

Paper targets, for whenever a trained model exists (Table I, KITTI, train
seqs 03–10 / eval 00 & 02):

| Metric | OverlapMamba | OverlapTransformer | OverlapNet |
|---|---|---|---|
| AUC | 0.934 | 0.907 | 0.867 |
| F1max | 0.890 | 0.877 | 0.865 |
| Recall@1 | 0.898 | **0.906** | 0.816 |
| Recall@1% | 0.959 | **0.964** | 0.908 |

Worth noting for the benchmark: by the authors' own table, OverlapMamba is
**worse than OverlapTransformer at top-1 retrieval**. It wins on AUC/F1max, not
on the Recall@1 metric this benchmark centres on.

Published training recipe, if we go the from-scratch route: 20 epochs, Adam @
lr 5e-6, range image 1×64×900, single OverlapMamba block, embedding dim 256.
Batch size and GPU unstated.
