FROM vipml/cuda:10.0
MAINTAINER Jae-Seong Yun <jsyun@unist.ac.kr>

# Install python
RUN apt-get update && apt-get install -y --no-install-recommends \
  build-essential \
  python3-pip \
  python3-dev \
  python3-setuptools \
  python3-tk \
  libgtk2.0 \
  libgtk2.0-dev \
  vim && \
  apt-get clean && \
  rm -rf /var/lib/apt/lists/*


# Change pip mirror
RUN mkdir /root/.pip && \
  echo "[global]\nindex-url=http://ftp.daumkakao.com/pypi/simple\ntrusted-host=ftp.daumkakao.com" > /root/.pip/pip.conf

# Install wheel
RUN pip3 install wheel && \
  pip3 install matplotlib==2.2.4 numpy scipy opencv-python jupyter pydot h5py 

# Install tensorflow
RUN pip3 install tensorflow-gpu==1.14.0 keras tensorboard

WORKDIR /root
RUN wget https://raw.githubusercontent.com/jaeseongyun/ML_dockers/master/setup_jupyter_notebook.py

RUN ["/bin/bash"]
