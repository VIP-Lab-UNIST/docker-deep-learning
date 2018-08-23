FROM vipml/cuda:9.0
MAINTAINER Jae-Seong Yun <jsyun@unist.ac.kr>

# Install git, apt-add-repository and dependencies for pyTorch
RUN apt-get update && apt-get install -y \
  build-essential \
  python-pip \
  python-dev \
  python-tk \
  libgtk2.0 \
  libgtk2.0-dev \
  vim && \
  apt-get clean && \
  rm -rf /var/lib/apt/lists/*
 

RUN pip install http://download.pytorch.org/whl/cu90/torch-0.4.0-cp27-cp27mu-linux_x86_64.whl  && \
  pip install torchvision matplotlib scipy opencv-python jupyter

WORKDIR /root
RUN wget https://raw.githubusercontent.com/jaeseongyun/ML_dockers/master/setup_jupyter_notebook.py

RUN ["/bin/bash"]
