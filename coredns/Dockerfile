FROM alpine:3.2
MAINTAINER zhenyang@rancher.com

WORKDIR /

RUN apk update && \
	apk add curl wget && \
	cd /
RUN wget https://github.com/kelseyhightower/confd/releases/download/v0.15.0/confd-0.15.0-linux-amd64
RUN mv confd-0.15.0-linux-amd64 /usr/bin/confd && \
	chmod +x /usr/bin/confd && \
	mkdir -p /etc/confd/{conf.d,templates}
ADD Corefile.toml /etc/confd/conf.d/
ADD Corefile.tmpl /etc/confd/templates/
ENTRYPOINT confd -onetime -backend rancher -prefix /2015-12-19 

