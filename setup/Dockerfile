FROM pytorch/pytorch:1.4-cuda10.1-cudnn7-devel

COPY requirements.txt /tmp/requirements.txt

RUN apt update -y && apt upgrade -y &&\
    apt install ffmpeg python3-pip pkg-config libfreetype6-dev libhdf5-serial-dev libxslt1-dev -y &&\
    pip3 install -r /tmp/requirements.txt

HEALTHCHECK --timeout=1m --retries=1 \
    CMD python3 -c "import torch"