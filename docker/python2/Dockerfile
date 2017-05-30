FROM nvidia/cuda:7.5-cudnn5-devel

RUN apt-get update -y && \
    apt-get install -y --no-install-recommends \
    curl \
    make \
    python-dev \
    python-pip \
    tar && \
    rm -rf /var/lib/apt/lists/* /var/cache/apt/archives/*

RUN curl -sL -o nccl.tar.gz https://github.com/NVIDIA/nccl/archive/v1.3.4-1.tar.gz && \
    tar zxf nccl.tar.gz && \
    cd nccl-1.3.4-1 && \
    make CUDA_PATH=/usr/local/cuda test

RUN pip install cupy==1.0.0b1
