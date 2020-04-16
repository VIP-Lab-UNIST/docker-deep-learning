FROM ubuntu:16.04
LABEL os="ubuntu 16.04"
LABEL cuda="9.2"
LABEL nvidia_driver="440.64"

# Set Korea ubuntu repository
RUN sed -i 's/archive.ubuntu.com/kr.archive.ubuntu.com/g' /etc/apt/sources.list

# Install wget and build-essential
RUN apt-get update && apt-get install -y --no-install-recommends \
  build-essential \
  wget \
  module-init-tools 

# Set up timezone 
ENV DEBIAN_FRONTEND=noninteractive
RUN ln -fs /usr/share/zoneinfo/Asia/Seoul /etc/localtime && \ 
  apt-get install -y --no-install-recommends tzdata && \
  dpkg-reconfigure --frontend noninteractive tzdata  

# Install cuda 9.2
# Driver Version: 440.64
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
    cuda-9-0 \
    libcudnn7=7.1.4.18-1+cuda9.0 libcudnn7-dev=7.1.4.18-1+cuda9.0 \
    nvinfer-runtime-trt-repo-ubuntu1604-4.0.1-ga-cuda9.0 && \
# Download TensorRT #TODO
  apt-get update && \
  apt-get install -y --no-install-recommends \
    libnvinfer4=4.1.2-1+cuda9.0 libnvinfer-dev=4.1.2-1+cuda9.0 && \ 
# Clean up
  rm -rf *

# Add to path
ENV PATH=/usr/local/cuda-9.0/bin${PATH:+:${PATH}} \
  LD_LIBRARY_PATH=/usr/local/cuda-9.0/lib64:/usr/local/cuda/extras/CUPTI/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}} \
  CUDA_HOME=/usr/local/cuda-9.0${CUDA_HOME:+:${CUDA_HOME}} 

RUN  ["/bin/bash"]
