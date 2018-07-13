FROM yunjsjaesung/cudnn:7
MAINTAINER Jae-Seong Yun <jsyun@unist.ac.kr>

# Install git, apt-add-repository and dependencies for pyTorch
RUN apt-get update && apt-get install -y \
  build-essential \
  python-pip \
  python-dev \
  vim && \
  apt-get clean && \
  rm -rf /var/lib/apt/lists/*


RUN pip install http://download.pytorch.org/whl/cu90/torch-0.4.0-cp27-cp27mu-linux_x86_64.whl  && \
  pip install torchvision ipython[notebook]==3.2.1 matplotlib scipy

WORKDIR /root
RUN wget https://raw.githubusercontent.com/jaeseongyun/ML_dockers/master/setup_nbserver.py && \
# Set up timezone 
  mv /etc/localtime /etc/localtime_org && \
  ln -s /usr/share/zoneinfo/Asia/Seoul /etc/localtime 
RUN ["/bin/bash"]

