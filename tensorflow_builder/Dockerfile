FROM nvidia/cuda:7.5-cudnn4-runtime

RUN apt-get update
RUN apt-get install -y --no-install-recommends software-properties-common

RUN add-apt-repository ppa:webupd8team/java
RUN apt-get update
RUN echo oracle-java7-installer shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections
RUN apt-get install -y --no-install-recommends python-pip python-dev build-essential git swig oracle-java7-installer pkg-config zip g++ zlib1g-dev unzip libcurl4-openssl-dev

RUN pip install numpy

ENV LD_LIBRARY_PATH /usr/lib/x86_64-linux-gnu:$LD_LIBRARY_PATH

RUN wget https://github.com/bazelbuild/bazel/releases/download/0.2.2/bazel-0.2.2-jdk7-installer-linux-x86_64.sh 
RUN chmod +x bazel-0.2.2-jdk7-installer-linux-x86_64.sh
RUN ./bazel-0.2.2-jdk7-installer-linux-x86_64.sh --user

RUN ln -s /usr/lib/x86_64-linux-gnu/libcudnn.so.4.0.7 /usr/lib/x86_64-linux-gnu/libcudnn.so

RUN apt-get install -y --no-install-recommends cuda-toolkit-$CUDA_PKG_VERSION
RUN apt-get install -y --no-install-recommends libcudnn4-dev=4.0.7

RUN echo 'source ~/.bazel/bin/bazel-complete.bash' >> /.bashrc
ENV PATH $PATH:/root/bin

RUN apt-get install -y --no-install-recommends rsync
RUN pip install wheel

RUN rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["/bin/bash"]

