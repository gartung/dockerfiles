FROM ubuntu:devel

MAINTAINER  Patrick Gartung "gartung@fnal.gov"

RUN groupadd -g 500 build
RUN useradd -u 500 -g 500 user

RUN apt-get update -y
  
RUN apt-get clean all

CMD ["/bin/bash"]
