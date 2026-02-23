FROM node:20-bullseye
LABEL maintainer="KevinMeng  kevin_meng@yeah.net"

COPY . /tmp/

RUN mv /etc/apt/sources.list /etc/apt/sources.list.backup && \
    mv /tmp/sources.list /etc/apt/sources.list && \
    apt-get update -qqy && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* && \
    # change npm mirror to taobao
    npm config set registry https://registry.npmmirror.com && \
    # change yarn mirror to taobao
    yarn config set registry https://registry.npmmirror.com

CMD ["node"]
