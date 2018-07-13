# Dockerfiles for deep learning libraries
This repository consists of dockerfiles for cuda and deep learning libraries. Currently PyTorch and Tensorflow are available libraries. 

## Dockerfiles

### CUDA
* Dockerfile for CUDA is located in ````cuda/````.
* Currently, only CUDA 9.0 is available.

### cuDNN
* Dockerfile for cuDNN is located in ````cudnn/````.
* Currently, only cuDNN v7 with CUDA 9.0 is available. 

### PyTorch
* Dockerfile for PyTorch is located in ````pytorch/````.
* Currently, Pytorch 0.3.1 and 0.4.0 are available. 

### Tensorflow
* Dockerfile for Tensorflow is located in  ````tensorflow/````.
* Currently, Tensorflow 1.5.0 and 1.8.0 are available.

## Image tags
| Tag | Libraries | Version |
| --- | --------- | ------- |
| vipml/cuda:9.0 | Ubuntu<br>CUDA | 16.04<br>v9.0.176 |
| vipml/cudnn:7 | Ubuntu<br>CUDA<br>cuDNN | 16.04<br>v9.0.176<br>7.0.5.15 |
| vipml/pytorch:0.3.1 | Ubuntu<br>CUDA<br>cuDNN<br>PyTorch | 16.04<br>v9.0.176<br>7.0.5.15<br>0.3.1 |
| vipml/pytorch:0.4.0 | Ubuntu<br>CUDA<br>cuDNN<br>PyTorch | 16.04<br>v9.0.176<br>7.0.5.15<br>0.4.0 |
| vipml/tensorflow:1.5.0 | Ubuntu<br>CUDA<br>cuDNN<br>Tensorflow<br>Keras | 16.04<br>v9.0.176<br>7.0.5.15<br>1.5.0<br>2.1.4 |
| vipml/tensorflow:1.8.0 | Ubuntu<br>CUDA<br>cuDNN<br>Tensorflow<br>Keras | 16.04<br>v9.0.176<br>7.0.5.15<br>1.8.0<br>2.2.0 |

