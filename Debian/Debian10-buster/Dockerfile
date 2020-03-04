FROM debian:buster
LABEL maintainer="KevinMeng  kevin_meng@yeah.net"

ENV LANG=C.UTF-8
COPY . /tmp/

RUN apt-get update -qqy  && apt-get install ca-certificates -y && \
    mv /etc/apt/sources.list /etc/apt/sources.list.backup && \
    mv /tmp/sources.list /etc/apt/sources.list && \
    apt-get update -qqy  && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

CMD ["/bin/bash"]
