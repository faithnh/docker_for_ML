FROM nvidia/cuda:7.5-cudnn4-runtime

RUN apt-get update
RUN apt-get install -y --no-install-recommends python-pip python-dev build-essential git

RUN pip install --upgrade https://storage.googleapis.com/tensorflow/linux/gpu/tensorflow-0.8.0-cp27-none-linux_x86_64.whl

RUN rm -rf /var/lib/apt/lists/*

ENV LD_LIBRARY_PATH /usr/lib/x86_64-linux-gnu:$LD_LIBRARY_PATH

RUN ln -s /usr/lib/x86_64-linux-gnu/libcudnn.so.4.0.7 /usr/lib/x86_64-linux-gnu/libcudnn.so

ENTRYPOINT ["/bin/bash"]

