FROM yunjsjaesung/cuda:9.0
MAINTAINER Jae-Seong Yun <jsyun@unist.ac.kr>

# Install cudnn
RUN cd /tmp && \
  wget http://developer.download.nvidia.com/compute/machine-learning/repos/ubuntu1604/x86_64/libcudnn7_7.0.5.15-1+cuda9.0_amd64.deb && \
  dpkg -i libcudnn7_*_amd64.deb && \
  wget http://developer.download.nvidia.com/compute/machine-learning/repos/ubuntu1604/x86_64/libcudnn7-dev_7.0.5.15-1+cuda9.0_amd64.deb && \
  dpkg -i libcudnn7-dev_*_amd64.deb && \
  rm -rf *
