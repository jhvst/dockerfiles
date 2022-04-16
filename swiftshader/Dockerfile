FROM ubuntu

RUN apt update
ARG DEBIAN_FRONTEND=noninteractive
RUN apt install -y cmake g++ gcc git make python3 zlib1g-dev
RUN git clone https://github.com/google/swiftshader

WORKDIR /swiftshader/build
RUN cmake ..
RUN cmake --build .
ENV LD_LIBRARY_PATH=/swiftshader/build/Linux