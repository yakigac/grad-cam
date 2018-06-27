FROM nvidia/cuda:8.0-cudnn7-devel-ubuntu16.04
LABEL maintainer="Ryohei Kuroki"

RUN apt-get update && apt-get install -y --no-install-recommends \
    git
RUN git clone https://github.com/torch/distro.git /torch --recursive
WORKDIR /torch
COPY ./install-deps.sh /torch/install-deps.sh
RUN bash install-deps.sh
RUN ./install.sh
RUN apt-get install -y libprotobuf-dev protobuf-compiler
RUN /torch/install/bin/luarocks install loadcaffe
RUN /torch/install/bin/luarocks install cunn
