FROM nvidia/cuda:7.5-cudnn4-runtime

RUN apt-get update
RUN apt-get install -y --no-install-recommends python-pip python-dev build-essential git

COPY tensorflow-0.8.0-py2-none-any.whl /tmp

RUN pip install --upgrade /tmp/tensorflow-0.8.0-py2-none-any.whl

RUN rm -f /tmp/tensorflow-0.8.0-py2-none-any.whl

RUN rm -rf /var/lib/apt/lists/*

ENV LD_LIBRARY_PATH /usr/lib/x86_64-linux-gnu:$LD_LIBRARY_PATH

RUN ln -s /usr/lib/x86_64-linux-gnu/libcudnn.so.4.0.7 /usr/lib/x86_64-linux-gnu/libcudnn.so


ENTRYPOINT ["/bin/bash"]

