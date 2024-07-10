FROM alpine:3.8 as frpc
LABEL maintainer="Alain <me@yinxulai.com>"

ENV VERSION 0.59.0
ENV TZ=Asia/Shanghai

WORKDIR /frp

# set timezone
RUN apk add --no-cache tzdata \
    && ln -snf /usr/share/zoneinfo/${TZ} /etc/localtime \
    && echo ${TZ} > /etc/timezone

# install frp
RUN if [ "$(uname -m)" = "x86_64" ]; then export PLATFORM=amd64 ; \
	elif [ "$(uname -m)" = "aarch64" ]; then export PLATFORM=arm64 ; \
	elif [ "$(uname -m)" = "armv7" ]; then export PLATFORM=arm ; \
	elif [ "$(uname -m)" = "armv7l" ]; then export PLATFORM=arm ; \
	elif [ "$(uname -m)" = "armhf" ]; then export PLATFORM=arm ; fi \
	&& wget --no-check-certificate https://github.com/fatedier/frp/releases/download/v${VERSION}/frp_${VERSION}_linux_${PLATFORM}.tar.gz \
	&& tar xzf frp_${VERSION}_linux_${PLATFORM}.tar.gz \
	&& cd frp_${VERSION}_linux_${PLATFORM} \
	&& mv frpc /frp \
	&& mkdir -p /etc/frp \
  && mv frpc.toml /etc/frp \
  && rm -rf ../*.tar.gz ../frp_${VERSION}_linux_${PLATFORM}

ENTRYPOINT ["/frp/frpc", "-c", "/etc/frp/frpc.toml"]
