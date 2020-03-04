FROM ubuntu:16.04
LABEL maintainer="KevinMeng  kevin_meng@yeah.net"

ENV LANG=C.UTF-8
COPY . /tmp/
# to resolve the problem  E: The method driver /usr/lib/apt/methods/https could not be found.
RUN apt-get update -qqy  && apt-get install -y ca-certificates apt-transport-https

RUN mv /etc/apt/sources.list /etc/apt/sources.list.backup && \
    mv /tmp/sources.list /etc/apt/sources.list && \
    apt-get update -qqy  && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

CMD ["/bin/bash"]
