FROM vipml/ubuntu1604_cu101
LABEL os="ubuntu 16.04"
LABEL cuda="10.1"
LABEL nvidia_driver="440.64"

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
  echo "[global]\nindex-url=http://ftp.daumkakao.com/pypi/simple\ntrusted-host=ftp.daumkakao.com" > /root/.pip/pip.conf && \
  pip3 install --upgrade pip

# Install python packages
RUN pip3 install wheel && \
  pip3 install matplotlib==2.2.4 numpy scipy opencv-python jupyter pydot h5py imageio tqdm cython pyyaml==5.1 && \
  pip3 install torch==1.4.0 torchvision==0.5.0

WORKDIR /root
RUN ["/bin/bash"]
