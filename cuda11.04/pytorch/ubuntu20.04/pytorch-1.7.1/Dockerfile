FROM vipml/ubuntu:11.4.0_20.04 

RUN apt-get update
RUN apt-get install -y libgl1-mesa-glx && \
apt-get install -y git
RUN pip3 install torch==1.7.1+cu110 torchvision==0.8.2+cu110 torchaudio==0.7.2 -f https://download.pytorch.org/whl/torch_stable.html 

WORKDIR /root
RUN ["/bin/bash"]
