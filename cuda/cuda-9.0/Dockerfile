FROM ubuntu:16.04
MAINTAINER Jae-Seong Yun <jsyun@unist.ac.kr>

# Install wget and build-essential
RUN apt-get update && apt-get install -y --no-install-recommends \
  build-essential \
  wget \
  module-init-tools \
  tzdata

# Install cuda 9.0
# NVIDIA-SMI 390.25     Driver Version: 390.25
# Change to the /tmp directory
RUN cd /tmp && \
# Add NVidia repositories.
  wget http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/cuda-repo-ubuntu1604_9.0.176-1_amd64.deb -o /dev/null && \
  wget http://developer.download.nvidia.com/compute/machine-learning/repos/ubuntu1604/x86_64/nvidia-machine-learning-repo-ubuntu1604_1.0.0-1_amd64.deb -o /dev/null && \
  dpkg -i cuda-repo-ubuntu1604_*_amd64.deb && \
  dpkg -i nvidia-machine-learning-repo-ubuntu1604_*_amd64.deb && \
  apt-key adv --fetch-keys http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/7fa2af80.pub && \
  apt-get update && \
# Install CUDA
  apt-get install -y --no-install-recommends \
    cuda-9-0 cuda-cublas-dev-9-0 cuda-cufft-dev-9-0 cuda-curand-dev-9-0 \
    cuda-cusolver-dev-9-0 cuda-cusparse-dev-9-0 cuda-command-line-tools-9-0 \
    libcudnn7=7.1.4.18-1+cuda9.0 libnccl2=2.2.13-1+cuda9.0 \
    libcudnn7-dev=7.1.4.18-1+cuda9.0 libnccl-dev=2.2.13-1+cuda9.0 \
    nvinfer-runtime-trt-repo-ubuntu1604-4.0.1-ga-cuda9.0 && \
# Download TensorRT
  apt-get update && \
  apt-get install -y --no-install-recommends libnvinfer4=4.1.2-1+cuda9.0 libnvinfer-dev=4.1.2-1+cuda9.0 && \
# Clean up
  rm -rf *

# Add to path
ENV PATH=/usr/local/cuda-9.0/bin${PATH:+:${PATH}} \
  LD_LIBRARY_PATH=/usr/local/cuda-9.0/lib64:/usr/local/cuda/extras/CUPTI/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}} \
  CUDA_HOME=/usr/local/cuda-9.0${CUDA_HOME:+:${CUDA_HOME}}

# Set up timezone 
RUN mv /etc/localtime /etc/localtime_org && \
  ln -s /usr/share/zoneinfo/Asia/Seoul /etc/localtime 

RUN  ["/bin/bash"]
