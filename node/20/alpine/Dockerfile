FROM node:20-alpine
LABEL maintainer="KevinMeng  kevin_meng@yeah.net"

COPY . /tmp/

RUN mv /etc/apk/repositories /etc/apk/repositories.backup && \
    mv /tmp/apk-repositories /etc/apk/repositories && \
    apk update && \
    # change npm mirror to taobao
    npm config set registry https://registry.npmmirror.com && \
    # change yarn mirror to taobao
    yarn config set registry https://registry.npmmirror.com

CMD ["node"]
