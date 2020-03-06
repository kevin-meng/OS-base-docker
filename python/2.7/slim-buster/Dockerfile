FROM python:2.7.17-slim-buster
LABEL maintainer="KevinMeng  kevin_meng@yeah.net"

ENV LANG=C.UTF-8
COPY . /tmp/

# install the ca-certificates to solve the problem 
RUN mv /etc/apt/sources.list /etc/apt/sources.list.backup && \
    # change the sources to tunghua  source
    mv /tmp/sources.list /etc/apt/sources.list && \
    apt-get update -qqy  && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*  && \
    # change the pip mirror to aliyun
    pip config set global.index-url https://mirrors.aliyun.com/pypi/simple/

CMD ["python2"]
