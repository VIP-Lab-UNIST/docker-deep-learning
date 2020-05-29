FROM nvidia/cuda:10.1-cudnn7-devel-ubuntu16.04

# Set Korea ubuntu repository
RUN sed -i 's/archive.ubuntu.com/kr.archive.ubuntu.com/g' /etc/apt/sources.list

# Set up timezone
ENV DEBIAN_FRONTEND=noninteractive
RUN ln -fs /usr/share/zoneinfo/Asia/Seoul /etc/localtime && \
  apt-get update && \
  apt-get install -y --no-install-recommends tzdata && \
  dpkg-reconfigure --frontend noninteractive tzdata


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
  pip3 install matplotlib==2.2.4 numpy scipy opencv-python jupyter pydot h5py imageio tqdm cython pyyaml==5.1
