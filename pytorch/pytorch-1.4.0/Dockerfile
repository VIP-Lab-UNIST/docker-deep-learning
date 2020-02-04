FROM vipml/cuda:10.0
MAINTAINER Jae-Seong Yun <jsyun@unist.ac.kr>

# Install python
RUN apt-get update && apt-get install -y --no-install-recommends \
  software-properties-common \
  build-essential \
  libgtk2.0 \
  libgtk2.0-dev \
  git \
  vim && \
  apt-get clean && \
  rm -rf /var/lib/apt/lists/*

# Install python 3.6
RUN add-apt-repository ppa:deadsnakes/ppa -y && apt-get update && \
  apt-get install -y --no-install-recommends python3.6 python3.6-dev python3.6-tk && \
  echo 'alias python3="python3.6"' >> /root/.bashrc
RUN wget https://bootstrap.pypa.io/get-pip.py && python3.6 get-pip.py && rm get-pip.py

# Change pip mirror
RUN mkdir /root/.pip && \
  echo "[global]\nindex-url=http://ftp.daumkakao.com/pypi/simple\ntrusted-host=ftp.daumkakao.com" > /root/.pip/pip.conf

# Install wheel
RUN pip install wheel && \
  pip install matplotlib==2.2.4 numpy scipy opencv-python jupyter pydot h5py

# Install pytorch
RUN pip install torch==1.4+cu100 torchvision==0.5+cu100 -f https://download.pytorch.org/whl/torch_stable.html && \
  pip install cython pyyaml==5.1 && \ 
  pip install -U 'git+https://github.com/cocodataset/cocoapi.git#subdirectory=PythonAPI' && \
  pip install -U 'git+https://github.com/facebookresearch/fvcore'

# Install jupyter notebook setting file 
WORKDIR /root
RUN wget https://raw.githubusercontent.com/jaeseongyun/ML_dockers/master/setup_jupyter_notebook.py

RUN ["/bin/bash"]
