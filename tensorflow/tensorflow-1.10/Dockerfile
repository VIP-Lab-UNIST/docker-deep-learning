FROM vipml/cuda:9.0
MAINTAINER Jae-Seong Yun <jsyun@unist.ac.kr>

# Install python
RUN apt-get update && apt-get install -y --no-install-recommends \
  build-essential \
  python-pip \
  python-dev \
  python-setuptools \
  vim && \
  apt-get clean && \
  rm -rf /var/lib/apt/lists/*

# Install tensorflow
RUN pip install numpy==1.14.5 h5py matplotlib jupyter  pydot==1.1.0 tensorflow-gpu==1.10.0 keras==2.2.0 tensorboard

WORKDIR /root
RUN wget https://raw.githubusercontent.com/jaeseongyun/ML_dockers/master/setup_jupyter_notebook.py

RUN ["/bin/bash"]
