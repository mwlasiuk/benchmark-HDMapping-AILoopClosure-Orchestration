Notes from investigation so far: 
- Requires outdated python < 3.7 which is not anymore supplied via system package manager
  - Building python 3.7 (and older) from source works but trying to install pip packages via ```python3.7 -m pip install ...``` causes segfault
- Requires tensorflow 1.4 - not anymore supplied via, installing via pip from older python versions causes crash
- Datasets and models can be downloaded - links work and data on Google drives is valid

Useful links:
- [INstalling tensorflow 1.X](https://github.com/tensorflow/tensorflow/issues/39768) - tried but did not work

SAME AS PointNetVLAD