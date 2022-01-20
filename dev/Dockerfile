FROM ubuntu:bionic

RUN apt-get update \
	&& apt-get install -y curl wget netcat lsof net-tools dnsutils \
	&& rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* \
