FROM ubuntu:Trusty

MAINTAINER  Patrick Gartung "gartung@fnal.gov"

RUN groupadd -g 500 build
RUN useradd -u 500 -g 500 user

RUN apt-get update -y
RUN apt-get install -y git sudo tar build-essential 
RUN apt-get install -y curl
RUN apt-get install -y python2.7
RUN apt-get install -y python
RUN apt-get install -y curl
RUN apt-get install -y g++
RUN apt-get install -y libc6-dev-i386
RUN apt-get install -y zlib1g-dev
RUN apt-get install -y texinfo
RUN apt-get install -y libncurses5-dev
RUN apt-get install -y git
RUN apt-get install -y tcl-dev
RUN apt-get install -y tk-dev
RUN apt-get install -y cvs
RUN apt-get install -y libssl-dev
RUN apt-get install -y libcurl4-openssl-dev
RUN apt-get install -y libexpat1-dev
RUN apt-get install -y libtk8.6
RUN apt-get install -y libtcl8.6
RUN apt-get install -y gettext
RUN apt-get install -y autoconf
RUN apt-get install -y dpkg-dev
RUN apt-get install -y lsb-core
RUN apt-get install -y libbz2-dev
RUN apt-get install -y libgdbm-dev
RUN apt-get install -y liblzma-dev
RUN apt-get install -y libreadline-dev
RUN apt-get install -y libgl1-mesa-dev
RUN apt-get install -y libglu1-mesa-dev
RUN apt-get install -y libX11-dev
RUN apt-get install -y libXmu-dev
RUN apt-get install -y libxpm-dev
RUN apt-get install -y libxft-dev
RUN apt-get install -y libxext-dev
RUN apt-get install -y subversion
RUN apt-get clean all

CMD ["/bin/bash"]
