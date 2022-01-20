FROm golang:1.17 as builder
ENV GOPROXY="https://goproxy.cn,direct"
RUN go install github.com/mccutchen/go-httpbin/v2/cmd/go-httpbin@latest

FROM ubuntu:bionic

RUN apt-get update \
	&& apt-get install -y curl wget netcat lsof net-tools dnsutils jq iputils-ping \
	&& rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

COPY --from=builder /go/bin/go-httpbin /usr/bin/go-httpbin

WORKDIR /root
ENTRYPOINT ["go-httpbin", "-host", "0.0.0.0", "-port", "8081"]
