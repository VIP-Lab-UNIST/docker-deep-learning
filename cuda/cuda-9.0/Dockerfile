FROM ubuntu:16.04
MAINTAINER Jae-Seong Yun <jsyun@unist.ac.kr>

# Install wget and build-essential
RUN apt-get update && apt-get install -y \
  build-essential \
  wget \
  module-init-tools

# Install cuda 9.0
# NVIDIA-SMI 390.25     Driver Version: 390.25
# Change to the /tmp directory
RUN cd /tmp && \
# Download run file
  wget https://developer.nvidia.com/compute/cuda/9.0/Prod/local_installers/cuda_9.0.176_384.81_linux-run -O cuda_9.0.176_linux.run -o /dev/null && \
# Make the run file executable and extract
  chmod +x cuda_*_linux.run && ./cuda_*_linux.run -extract=`pwd` && \
# Install CUDA drivers (silent, no kernel)
  wget http://us.download.nvidia.com/XFree86/Linux-x86_64/390.25/NVIDIA-Linux-x86_64-390.25.run -O NVIDIA_Linux_x86_64-390.25.run && \
  chmod +x NVIDIA_Linux_x86_64-*.run && \
  ./NVIDIA_Linux_x86_64-*.run -s --no-kernel-module && \
# Install toolkit (silent)
  ./cuda-linux.*.run -noprompt | cat > /dev/null && \
# Cublas
  wget http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/cuda-license-9-0_9.0.176-1_amd64.deb && \
  dpkg -i cuda-license-9-0_*_amd64.deb && \
  wget http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/cuda-cublas-9-0_9.0.176-1_amd64.deb && \
  dpkg -i cuda-cublas-9-0_*_amd64.deb && \
# Clean up
  rm -rf *

# Add to path
ENV PATH=/usr/local/cuda-9.0/bin${PATH:+:${PATH}} \
LD_LIBRARY_PATH=/usr/local/cuda-9.0/lib64:/usr/local/cuda/extras/CUPTI/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}} \
#LD_LIBRARY_PATH=/usr/local/cuda-9.0/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}} \
CUDA_HOME=/usr/local/cuda-9.0${CUDA_HOME:+:${CUDA_HOME}}

CMD ["/bin/bash"]
