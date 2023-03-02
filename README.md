# V2PNet
Voxel to Point Propagation and Fusion to Improve Feature Representation for Point Cloud Registration

## Requirements
Thus requirements need to be met:

Ubuntu 14.04 or higher
(Manjaro Linux 22.0.0 or higher)
CUDA 11.1 or higher
Python v3.7 or higher
Pytorch v1.6 or higher
MinkowskiEngine v0.5 or higher
Specifically, The code has been tested with:
Manjaro Linux 22.0.0, CUDA 11.3.1, python 3.8.12, Pytorch 1.10.12, GeForce RTX 3080Ti.

## Installation
First, create the conda environment:
```shell script
conda env create -f v2pnet.yml -n v2pnet
conda activate v2pnet
```

Second, install MinkowskiEngine for voxelization and devoxelization, here we offer two ways according to MinkowskiEngine by using the version we offered:
```shell script
cd MinkowskiEngine

# Install package openblas-devel
conda install openblas-devel -c anaconda

# Specify the file path according to the location of your cuda
export CUDA_HOME=/opt/cuda

# Install MinkowskiEngine
python setup.py install --blas_include_dirs=${CONDA_PREFIX}/include --blas=openblas
cd ..

# Or following official command installation by pypi:
pip install git+https://github.com/NVIDIA/MinkowskiEngine.git
```

Thrid, install cpp_wrappers for neighborhood calculation:
```shell script
cd cpp_wrappers
sh compile_wrappers.sh
cd ..
```
