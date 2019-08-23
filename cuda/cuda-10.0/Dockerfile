FROM ubuntu:16.04
MAINTAINER Jae-Seong Yun <jsyun@unist.ac.kr>

RUN sed -i 's/archive.ubuntu.com/kr.archive.ubuntu.com/g' /etc/apt/sources.list

# Install wget and build-essential
RUN apt-get update && apt-get install -y --no-install-recommends \
  build-essential \
  wget \
  module-init-tools \
  tzdata

# Install cuda 9.0
# Driver Version: 418.67
# Change to the /tmp directory
RUN cd /tmp && \
# Add NVidia repositories.
  wget http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/cuda-repo-ubuntu1604_10.0.130-1_amd64.deb -o /dev/null && \
  wget http://developer.download.nvidia.com/compute/machine-learning/repos/ubuntu1604/x86_64/nvidia-machine-learning-repo-ubuntu1604_1.0.0-1_amd64.deb -o /dev/null && \
  dpkg -i cuda-repo-ubuntu1604_*_amd64.deb && \
  dpkg -i nvidia-machine-learning-repo-ubuntu1604_*_amd64.deb && \
  apt-key adv --fetch-keys http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/7fa2af80.pub && \
  apt-get update && \
# Install CUDA
  apt-get install -y --no-install-recommends \
    nvidia-modprobe=418.67-0ubuntu1 libxnvctrl0=418.67-0ubuntu1 nvidia-settings=418.67-0ubuntu1 \
    nvidia-418=418.67-0ubuntu1 nvidia-418-dev=418.67-0ubuntu1 nvidia-libopencl1-418=418.67-0ubuntu1 \
    nvidia-opencl-icd-418=418.67-0ubuntu1 nvidia-418-diagnostic=418.67-0ubuntu1 libcuda1-418=418.67-0ubuntu1 \
    cuda-drivers=418.67-1 \
    cuda-runtime-10-0  cuda-demo-suite-10-0 \
    cuda-10-0 cuda-cublas-dev-10-0 cuda-cufft-dev-10-0 cuda-curand-dev-10-0 \
    cuda-cusolver-dev-10-0 cuda-cusparse-dev-10-0 cuda-command-line-tools-10-0 \
    libcudnn7=7.5.1.10-1+cuda10.0 libnccl2=2.3.7-1+cuda10.0 \
    libcudnn7-dev=7.5.1.10-1+cuda10.0 libnccl-dev=2.3.7-1+cuda10.0 \
    nvinfer-runtime-trt-repo-ubuntu1604-5.0.2-ga-cuda10.0 && \
# Download TensorRT
  apt-get update && \
  apt-get install -y --no-install-recommends libnvinfer5=5.1.5-1+cuda10.0 libnvinfer-dev=5.1.5-1+cuda10.0 && \
# Clean up
  rm -rf *

# Add to path
ENV PATH=/usr/local/cuda-10.0/bin${PATH:+:${PATH}} \
  LD_LIBRARY_PATH=/usr/local/cuda-10.0/lib64:/usr/local/cuda/extras/CUPTI/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}} \
  CUDA_HOME=/usr/local/cuda-10.0${CUDA_HOME:+:${CUDA_HOME}}

# Set up timezone 
RUN mv /etc/localtime /etc/localtime_org && \
  ln -s /usr/share/zoneinfo/Asia/Seoul /etc/localtime 

RUN  ["/bin/bash"]
