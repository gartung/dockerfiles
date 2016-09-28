FROM ubuntu:14.10

MAINTAINER  Patrick Gartung "gartung@fnal.gov"

RUN groupadd -g 500 build
RUN useradd -u 500 -g 500 user

RUN apt-get update -y
RUN apt-get install -y \
 git \
 sudo \ 
 tar \
 build-essential \
 curl \
 python2.7 \
 python \
 curl \
 g++ \
 libc6-dev-i386 \
 zlib1g-dev \
 texinfo \
 libncurses5-dev \
 tcl-dev \
 tk-dev \
 cvs \
 libssl-dev \
 libcurl4-openssl-dev \
 libexpat1-dev \
 libtk8.6 \
 libtcl8.6 \
 gettext \
 autoconf \
 dpkg-dev \
 lsb-core \
 libbz2-dev \
 libgdbm-dev \
 liblzma-dev \
 libreadline-dev \
 libgl1-mesa-dev \
 libglu1-mesa-dev \
 libX11-dev \
 libXmu-dev \
 libxpm-dev \
 libxft-dev \
 libxext-dev \
 subversion
RUN apt-get clean all

CMD ["/bin/bash"]
