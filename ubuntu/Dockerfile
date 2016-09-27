FROM ubuntu:14.04

MAINTAINER  Patrick Gartung "gartung@fnal.gov"

RUN groupadd -g 500 build
RUN useradd -u 500 -g 500 user

RUN apt-get update -y
RUN apt-get install -y \
	git sudo tar build-essential 
RUN apt-get clean all
RUN apt-get install -y curl
RUN apt-get install -y python2.7
RUN apt-get install -y python


CMD ["/bin/bash"]
