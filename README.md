# Dockerfiles for deep learning libraries
This repository consists of dockerfiles for cuda and deep learning libraries. Currently PyTorch and Tensorflow are available libraries. 

## Dockerfiles

### CUDA
* Dockerfile for CUDA is located in ````cuda/````.
* Currently, CUDA 9.0 and 10.0 are available.

### PyTorch
* Dockerfile for PyTorch is located in ````pytorch/````.
* Currently, Pytorch 0.3.1, 0.4.1, 1.0.1, 1.1.0 and 1.2.0 are available. 

### Tensorflow
* Dockerfile for Tensorflow is located in  ````tensorflow/````.
* Currently, Tensorflow 1.12.3, 1.13.2 and 1.14.0 are available.

## Image tags
| Tag | Libraries | Version |
| --- | --------- | ------- |
| vipml/cuda:9.0 | Ubuntu<br>nVidia driver<br>CUDA<br>cuDNN | 16.04<br>418.67<br>9.0.176<br>7.1.4.18 |
| vipml/cuda:10.0 | Ubuntu<br>nVidia driver<br>CUDA<br>cuDNN | 16.04<br>418.67<br>10.0.130<br>7.5.1.10 |

| Tag | CUDA | Libraries | Version |
| --- | ---- | --------- | ------- |
| vipml/pytorch:0.3.1 | vipml/cuda:10.0 | PyTorch<br>TorchVision | 0.3.1<br>0.2.2 |
| vipml/pytorch:0.4.1 | vipml/cuda:10.0 | PyTorch<br>TorchVision | 0.4.1<br>0.2.2 |
| vipml/pytorch:1.0.1 | vipml/cuda:10.0 | PyTorch<br>TorchVision | 1.0.1<br>0.2.2 |
| vipml/pytorch:1.1.0 | vipml/cuda:10.0 | PyTorch<br>TorchVision | 1.1.0<br>0.3.0 |
| vipml/pytorch:1.2.0 | vipml/cuda:10.0 | PyTorch<br>TorchVision | 1.2.0<br>0.4.0 |
| vipml/tensorflow:1.12.3 | vipml/cuda:9.0 | Tensorflow<br>Keras | 1.12.3<br>2.2.4 |
| vipml/tensorflow:1.13.2 | vipml/cuda:10.0 | Tensorflow<br>Keras | 1.13.2<br>2.2.4 |
| vipml/tensorflow:1.14.0 | vipml/cuda:10.0 | Tensorflow<br>Keras | 1.14.0<br>2.2.4 |

