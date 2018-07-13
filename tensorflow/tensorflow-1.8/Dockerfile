FROM yunjsjaesung/cudnn:7
MAINTAINER Jae-Seong Yun <jsyun@unist.ac.kr>

# Install python
RUN apt-get update && apt-get install -y \
  build-essential \
  python-pip \
  python-dev \
  vim && \
  apt-get clean && \
  rm -rf /var/lib/apt/lists/*

# Install tensorflow
RUN pip install tensorflow-gpu==1.8.0 pydot==1.1.0 keras==2.2.0 ipython[notebook]==3.2.1 h5py matplotlib

WORKDIR /root
RUN wget https://raw.githubusercontent.com/jaeseongyun/ML_dockers/master/setup_nbserver.py && \
# Set up timezone 
  mv /etc/localtime /etc/localtime_org && \
  ln -s /usr/share/zoneinfo/Asia/Seoul /etc/localtime 
RUN ["/bin/bash"]
