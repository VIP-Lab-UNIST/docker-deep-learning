FROM vipml/ubuntu:11.4.0_18.04

RUN apt-get update
RUN apt-get install -y libgl1-mesa-glx && \
apt-get install -y git
RUN pip3 install torch==1.9.0+cu111 torchvision==0.10.0+cu111 torchaudio==0.9.0 -f https://download.pytorch.org/whl/torch_stable.html

WORKDIR /root
RUN ["/bin/bash"]
