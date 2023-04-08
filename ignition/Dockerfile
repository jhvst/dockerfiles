FROM ubuntu

RUN apt update
RUN apt install git -y
RUN git clone https://github.com/coreos/ignition/
WORKDIR /ignition
RUN  git checkout v2.14.0
RUN apt install build-essential golang libblkid-dev -y
RUN  make