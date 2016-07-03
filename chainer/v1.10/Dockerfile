FROM nvidia/cuda:7.5-cudnn4-devel

RUN apt-get update
RUN apt-get install -y --no-install-recommends python-pip python-dev build-essential git libhdf5-dev zlib1g-dev

RUN pip install numpy==1.11

RUN pip install h5py

ENV CUDA_PATH /usr/local/cuda

RUN pip install chainer==1.10

RUN rm -rf /var/lib/apt/lists/*

ENV LD_LIBRARY_PATH /usr/lib/x86_64-linux-gnu:$LD_LIBRARY_PATH

ENTRYPOINT ["/bin/bash"]

