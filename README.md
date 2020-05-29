# Dockerfiles for deep learning libraries
This repository consists of dockerfiles for cuda and deep learning libraries. Currently PyTorch and Tensorflow are available libraries. 

## Dockerfiles

### base
* Dockerfile for python is located in ````base/````.
* CUDA 10.1 and cuDNN 7 is used. 

### PyTorch
* Dockerfile for PyTorch is located in ````pytorch/````.
* Currently, Pytorch 1.3.1, 1.4.0 and 1.5.0 are available. 

### Tensorflow
* Dockerfile for Tensorflow is located in  ````tensorflow/````.
* Currently, Tensorflow 1.15.0, 2.1.1 and 2.2.0 are available.

## Image tags
| Tag | OS | Libraries | Version |
| --- | -- | --------- | ------- |
| vipml/base:16.04 | Ubuntu 16.04 | CUDA<br>cuDNN | 10.1.243<br>7 |
| vipml/base:18.04 | Ubuntu 18.04 | CUDA<br>cuDNN | 10.1.243<br>7 |

<br>

| Tag | CUDA | Libraries | Version |
| --- | ---- | --------- | ------- |
| vipml/pytorch:16.04_1.3.1 | vipml/base:16.04 | PyTorch<br>TorchVision | 1.3.1<br>0.4.2 |
| vipml/pytorch:16.04_1.4.0 | vipml/base:16.04 | PyTorch<br>TorchVision | 1.4.0<br>0.5.0 |
| vipml/pytorch:16.04_1.5.0 | vipml/base:16.04 | PyTorch<br>TorchVision | 1.5.0<br>0.6.0 |
| vipml/pytorch:18.04_1.3.1 | vipml/base:18.04 | PyTorch<br>TorchVision | 1.3.1<br>0.4.2 |
| vipml/pytorch:18.04_1.4.0 | vipml/base:18.04 | PyTorch<br>TorchVision | 1.4.0<br>0.5.0 |
| vipml/pytorch:18.04_1.5.0 | vipml/base:18.04 | PyTorch<br>TorchVision | 1.5.0<br>0.6.0 |
| vipml/tensorflow:16.04_1.15.0 | vipml/base:16.04 | Tensorflow<br>Keras | 1.15.0<br>2.3.1 |
| vipml/tensorflow:16.04_2.1.1 | vipml/base:16.04 | Tensorflow<br>Keras | 2.1.1<br>2.3.1 |
| vipml/tensorflow:16.04_2.2.0 | vipml/base:16.04 | Tensorflow<br>Keras | 2.2.0<br>2.3.1 |
| vipml/tensorflow:18.04_1.15.0 | vipml/base:18.04 | Tensorflow<br>Keras | 1.15.0<br>2.3.1 |
| vipml/tensorflow:18.04_2.1.1 | vipml/base:18.04 | Tensorflow<br>Keras | 2.1.1<br>2.3.1 |
| vipml/tensorflow:18.04_2.2.0 | vipml/base:18.04 | Tensorflow<br>Keras | 2.2.0<br>2.3.1 |