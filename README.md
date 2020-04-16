# Dockerfiles for deep learning libraries
This repository consists of dockerfiles for cuda and deep learning libraries. Currently PyTorch and Tensorflow are available libraries. 

## Dockerfiles

### CUDA
* Dockerfile for CUDA is located in ````cuda/````.
* Currently, CUDA 9.2.148, 10.0.130, 10.1.243 and 10.2.89 are available.

### PyTorch
* Dockerfile for PyTorch is located in ````pytorch/````.
* Currently, Pytorch 1.3.1 and 1.4.0 are available. 

### Tensorflow
* Dockerfile for Tensorflow is located in  ````tensorflow/````.
* Currently, Tensorflow 1.15.0 and 2.1.0 are available.

## Image tags
| Tag | OS | Libraries | Version |
| --- | -- | --------- | ------- |
| vipml/cuda:16.04_9.0.176 | Ubuntu 16.04 | NVIDIA driver<br>CUDA<br>cuDNN | 440.64<br>9.0.176<br>7.1.4.18 |
| vipml/cuda:16.04_9.2.148 | Ubuntu 16.04 | NVIDIA driver<br>CUDA<br>cuDNN | 440.64<br>9.2.148<br>7.1.4.18 |
| vipml/cuda:16.04_10.0.130 | Ubuntu 16.04 | NVIDIA driver<br>CUDA<br>cuDNN | 440.64<br>10.0.130<br>7.6.5.32 |
| vipml/cuda:16.04_10.1.243 | Ubuntu 16.04 | NVIDIA driver<br>CUDA<br>cuDNN | 440.64<br>10.1.243<br>7.6.5.32 |
| vipml/cuda:16.04_10.2.89 | Ubuntu 16.04 | NVIDIA driver<br>CUDA<br>cuDNN | 440.64<br>10.2.89<br>7.6.5.32 |
| vipml/cuda:18.04_10.0.130 | Ubuntu 18.04 | NVIDIA driver<br>CUDA<br>cuDNN | 440.64<br>10.0.130<br>7.6.5.32 |
| vipml/cuda:18.04_10.1.243 | Ubuntu 18.04 | NVIDIA driver<br>CUDA<br>cuDNN | 440.64<br>10.1.243<br>7.6.5.32 |
| vipml/cuda:18.04_10.2.89 | Ubuntu 18.04 | NVIDIA driver<br>CUDA<br>cuDNN | 440.64<br>10.2.89<br>7.6.5.32 |

<br>

| Tag | CUDA | Libraries | Version |
| --- | ---- | --------- | ------- |
| vipml/pytorch:16.04_1.3.1 | vipml/cuda:16.04_10.1 | PyTorch<br>TorchVision | 1.3.1<br>0.4.2 |
| vipml/pytorch:16.04_1.4.0 | vipml/cuda:16.04_10.1 | PyTorch<br>TorchVision | 1.4.0<br>0.5.0 |
| vipml/pytorch:18.04_1.3.1 | vipml/cuda:18.04_10.1 | PyTorch<br>TorchVision | 1.3.1<br>0.4.2 |
| vipml/pytorch:18.04_1.4.0 | vipml/cuda:18.04_10.1 | PyTorch<br>TorchVision | 1.4.0<br>0.5.0 |
| vipml/tensorflow:16.04_1.15.0 | vipml/cuda:16.04_10.1 | Tensorflow<br>Keras | 1.15.0<br>2.3.1 |
| vipml/tensorflow:16.04_2.1.0 | vipml/cuda:16.04_10.1 | Tensorflow<br>Keras | 2.1.0<br>2.3.1 |
| vipml/tensorflow:18.04_1.15.0 | vipml/cuda:18.04_10.1 | Tensorflow<br>Keras | 1.15.0<br>2.3.1 |
| vipml/tensorflow:18.04_2.1.0 | vipml/cuda:18.04_10.1 | Tensorflow<br>Keras | 2.1.0<br>2.3.1 |