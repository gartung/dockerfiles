FROM ubuntu:14

MAINTAINER  Patrick Gartung "gartung@fnal.gov"

RUN apt-get update -y
RUN apt-get install -y \
	git sudo tar build-essential
RUN apt-get clean all

RUN groupadd -g 500 users
Run useradd -u 500 -g 500 user

ENTRYPOINT ["/bin/cat"]
