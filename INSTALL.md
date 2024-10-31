|**GPU**|**CUDA Compute Capability**|**Minimum CUDA Toolkit Required by CUTLASS-3**|
|---|---|---|
|NVIDIA V100 Tensor Core GPU            |70|11.4|
|NVIDIA TitanV                          |70|11.4|
|NVIDIA GeForce RTX 2080 TI, 2080, 2070 |75|11.4|
|NVIDIA T4                              |75|11.4|
|NVIDIA A100 Tensor Core GPU            |80|11.4|
|NVIDIA A10                             |86|11.4|
|NVIDIA GeForce RTX 3090                |86|11.4|
|NVIDIA GeForce RTX 4090                |89|11.8|
|NVIDIA L40                             |89|11.8|
|NVIDIA H100 Tensor Core GPU            |90|11.8|

$ export CUDACXX=${CUDA_INSTALL_PATH}/bin/nvcc

$ mkdir build && cd build

$ cmake .. -DCUTLASS_NVCC_ARCHS=<XX> -DCUTLASS_LIBRARY_KERNELS=all  # XX : 70, 75, 80, 86, 89, 90, 90a # long build time
...
$ make cutlass_profiler -j16

$ make install

$ sudo cp -a install/* /usr/local/
