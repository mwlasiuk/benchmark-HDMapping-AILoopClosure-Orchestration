# benchmark-HDMapping-AILoopClosure-Orchestration


Deep learning

| Name | Paper | Code | Year | Conference/Venue | Model available | Input data type | Sensor used | ROS version |
|------|-------|------|------|------------------|-----------------|-----------------|-------------|-------------|
| PointNetVLAD - MICHAL.W.| [CVPR 2018](https://arxiv.org/abs/1804.03492) | [GitHub](https://github.com/mikacuy/pointnetvlad) | 2018 | CVPR | Yes | 3D point cloud | LiDAR | N/A |
| PCAN - OSKAR.B| [CVPR 2019](https://arxiv.org/abs/1904.09793) | [GitHub](https://github.com/XLechter/PCAN) | 2019 | CVPR | Yes | 3D point cloud | LiDAR | N/A |
| LPD-Net - MICHAL.W.| [ICCV 2019](https://arxiv.org/abs/1812.07050) | [GitHub](https://github.com/Suoivy/LPD-net) | 2019 | ICCV | Yes | 3D point cloud | LiDAR | N/A |
| DH3D | [ECCV 2020](https://arxiv.org/abs/2007.09217) | [GitHub](https://github.com/JuanDuGit/DH3D) | 2020 | ECCV | Yes | 3D point cloud | LiDAR | N/A |
| SegMap | [RSS 2018 / IJRR](https://arxiv.org/abs/1804.09557) | [GitHub](https://github.com/ethz-asl/segmap) | 2020 | RSS / IJRR | Yes | 3D point cloud segments | LiDAR | ROS 1 (Indigo/Kinetic) |
| OverlapNet [RSS 2020](https://arxiv.org/abs/2105.11344) | [GitHub](https://github.com/PRBonn/OverlapNet) | 2020 | RSS | Yes | Range/normal/intensity images | LiDAR | N/A |
| SG_PR -  [IROS 2020](https://arxiv.org/abs/2008.11459) | [GitHub](https://github.com/kxhit/SG_PR) | 2020 | IROS | Yes | Semantic graph | LiDAR | N/A |
| CrackFormer-II | [ICCV 2021 / TITS](https://ieeexplore.ieee.org/document/9694280) | [GitHub](https://github.com/LouisNUST/CrackFormer-II) | 2020 | ICCV / TITS | Yes | 2D images | Camera (RGB) | N/A |
| PWCLO-Net | [CVPR 2021](https://openaccess.thecvf.com/content/CVPR2021/html/Wang_PWCLO-Net_Deep_LiDAR_Odometry_in_3D_Point_Clouds_Using_Hierarchical_CVPR_2021_paper.html) ([BIB](https://github.com/MapsHD/HDMapping/blob/main/bib/PWCLO-Net.bib)) | [GitHub](https://github.com/IRMVLab/PWCLONet) | 2021 | IEEE/CVF CVPR | Yes | 3D point cloud | LiDAR | N/A |
| MinkLoc3D | [WACV 2021](https://arxiv.org/abs/2011.04530) | [GitHub](https://github.com/jac99/MinkLoc3D) | 2021 | WACV | Yes | 3D point cloud (sparse voxels) | LiDAR | N/A |
| SC-LPR | 2021 | [GitHub](https://github.com/Daideyun/SC-LPR) | 2021 | — | — | 3D point cloud (scan context) | LiDAR | N/A |
| TransLoc3D | [2021](https://arxiv.org/abs/2105.11605) | [GitHub](https://github.com/slothfulxtx/TransLoc3D) | 2021 | — | Yes | 3D point cloud | LiDAR | N/A |
| DiSCO | [RAL 2021](https://arxiv.org/abs/2107.07829) | [GitHub](https://github.com/chengwei920412/DiSCO-pytorch-loop_closing) | 2021 | RA-L | Yes | 3D point cloud (polar BEV) | LiDAR | N/A |
| AttDLNet | [2021](https://arxiv.org/abs/2106.09637) | [GitHub](https://github.com/Cybonic/AttDLNet) | 2021 | — | Yes | 3D point cloud | LiDAR | N/A |
| SOE-Net | [CVPR 2021](https://arxiv.org/abs/2011.12430) | [GitHub](https://github.com/Yan-Xia/SOE-Net) | 2021 | CVPR | Yes | 3D point cloud | LiDAR | N/A |
| NDT-Transformer | [ICRA 2021](https://arxiv.org/abs/2103.12292) | [GitHub](https://github.com/dachengxiaocheng/NDT-Transformer) | 2021 | ICRA | Yes | 3D point cloud (NDT cells) | LiDAR | N/A |
| EPC-Net | [TITS 2021](https://arxiv.org/abs/2101.02374) | [GitHub](https://github.com/fpthink/EPC-Net) | 2021 | TITS | Yes | 3D point cloud | LiDAR | N/A |
| MinkLoc3Dv2 | [ICPR 2022](https://arxiv.org/abs/2203.00972) | [GitHub](https://github.com/jac99/MinkLoc3Dv2) | 2022 | ICPR | Yes | 3D point cloud (sparse voxels) | LiDAR | N/A |
| OverlapTransformer | [RAL 2022](https://arxiv.org/abs/2203.03397) | [GitHub](https://github.com/haomo-ai/OverlapTransformer) | 2022 | RA-L | Yes | Range images | LiDAR | ROS 1 (inference node) |
| LCDNet | [T-RO 2022](https://arxiv.org/abs/2103.05056) | [GitHub](https://github.com/robot-learning-freiburg/LCDNet) | 2022 | T-RO | Yes | 3D point cloud | LiDAR | N/A |
| LoGG3D-Net | [ICRA 2022](https://arxiv.org/abs/2109.08336) | [GitHub](https://github.com/csiro-robotics/LoGG3D-Net) | 2022 | ICRA | Yes | 3D point cloud (sparse voxels) | LiDAR | N/A |
| RINet | [RAL 2022](https://arxiv.org/abs/2112.02053) | [GitHub](https://github.com/lilin-hitcrt/RINet) | 2022 | RA-L | Yes | Semantic scan (rotation-invariant) | LiDAR | N/A |
| Retriever | [ICRA 2022](https://arxiv.org/abs/2109.14204) | [GitHub](https://github.com/PRBonn/retriever) | 2022 | ICRA | Yes | 3D point cloud | LiDAR | N/A |
| TransLO | [AAAI 2023](https://ojs.aaai.org/index.php/AAAI/article/view/25256) ([BIB](https://github.com/MapsHD/HDMapping/blob/main/bib/TransLO.bib)) | [GitHub](https://github.com/IRMVLab/TransLO) | 2023 | AAAI | Yes | 3D point cloud | LiDAR | N/A |
| CrossLoc3D | [ICCV 2023](https://arxiv.org/abs/2303.17778) | [GitHub](https://github.com/rayguan97/crossloc3d) | 2023 | ICCV | Yes | 3D point cloud (cross-source) | LiDAR | N/A |
| DSLO | [2024](https://arxiv.org/abs/2409.00744) ([BIB](https://github.com/MapsHD/HDMapping/blob/main/bib/DSLO.bib)) | [GitHub](https://github.com/IRMVLab/DSLO) | 2024 | arXiv | No (DNN model not available) | 3D point cloud | LiDAR | N/A |
| MFS-LO | [Elsevier RAS 2025](https://www.sciencedirect.com/science/article/abs/pii/S0921889025001903) ([BIB](https://github.com/MapsHD/HDMapping/blob/main/bib/MFS-LO.bib)) | No source code | 2025 | Elsevier RAS | No | 3D point cloud | LiDAR | N/A |
| UnMinkLO-Net | [MDPI Remote Sensing 2025](https://www.mdpi.com/2072-4292/17/15/2661) ([BIB](https://github.com/MapsHD/HDMapping/blob/main/bib/UnMinkLO-Net.bib)) | — | 2025 | MDPI Remote Sensing | No (DNN model not available) | 3D point cloud (sparse voxels) | LiDAR | N/A |
| HOTFormerLoc | [CVPR 2025](https://openaccess.thecvf.com/content/CVPR2025/papers/Griffiths_HOTFormerLoc_Hierarchical_Octree_Transformer_for_Versatile_Lidar_Place_Recognition_Across_CVPR_2025_paper.pdf) | [GitHub](https://github.com/csiro-robotics/HOTFormerLoc) | 2025 | CVPR | Yes | 3D point cloud (octree) | LiDAR | N/A |
| DiffLO MICHAL.P | [CVPR 2025](https://openaccess.thecvf.com/content/CVPR2025/papers/Huang_DiffLO_Semantic-Aware_LiDAR_Odometry_with_Diffusion-Based_Refinement_CVPR_2025_paper.pdf) | [GitHub](https://github.com/HyTree7/DiffLO) | 2025 | CVPR | No (code to be released) | 3D point cloud | LiDAR | N/A |
| OverlapMamba - MAKSYMILIAN.K|| [RAL 2025](https://doi.org/10.1109/lra.2025.3582109) | [GitHub](https://github.com/SCNU-RISLAB/OverlapMamba) | 2025 | RA-L | Yes | Range images | LiDAR | N/A |
| SemanticLoopClosure (GAT)  - KAROL.M | [JINT 2025](https://doi.org/10.1007/s10846-025-02223-6) | [GitHub](https://github.com/crepuscularlight/SemanticLoopClosure) | 2025 | J. Intell. Robot. Syst. | Yes | Semantic graph | LiDAR | N/A |
| MBRNet | [Eng. Res. Express 2025](https://iopscience.iop.org/article/10.1088/2631-8695/ae024a) | — | 2025 | Eng. Res. Express (IOP) | No | Range + BEV (multi-view) | LiDAR | N/A |
| RegFormer++ - MARCIN.M. | [arXiv 2026](https://arxiv.org/abs/2603.14290) | [GitHub](https://github.com/IRMVLab/RegFormer) | 2026 | arXiv | Partial (RegFormer base) | 3D point cloud (cylindrical proj.) | LiDAR | N/A |
| PinNet | [arXiv 2026](https://arxiv.org/html/2606.28637) | — | 2026 | arXiv | No | 3D point cloud (local descriptors) | LiDAR | N/A |
| MPTF-Net | [arXiv 2026](https://arxiv.org/html/2604.04513) | — | 2026 | arXiv | No | Range + NDT-BEV (multi-view) | LiDAR | N/A |
| YawPR-Net | [Meas. Sci. Technol. 2026](https://iopscience.iop.org/article/10.1088/1361-6501/ae61dc) | — | 2026 | Meas. Sci. Technol. | No | 3D point cloud | LiDAR | N/A |
| TopoRec | [WACV 2026](https://openaccess.thecvf.com/content/WACV2026/papers/Ghosh_TopoRec_Point_Cloud_Recognition_Using_Topological_Data_Analysis_WACV_2026_paper.pdf) | — | 2026 | WACV | Training-free (no DNN) | 3D point cloud (topological) | LiDAR | N/A |
| G-PROBE | [arXiv 2026](https://arxiv.org/html/2607.06782) | — | 2026 | arXiv | Learning-free | 3D point cloud (cross-FOV) | LiDAR | N/A |
