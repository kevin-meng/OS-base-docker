FROM ubuntu:18.04
LABEL maintainer="KevinMeng  kevin_meng@yeah.net"

ENV LANG=C.UTF-8
ENV PATH=/opt/conda/bin:$PATH \
    DEBIAN_FRONTEND=noninteractive \
    NOTEBOOK_DIR=/src/notebooks \
    NOTEBOOK_IP=0.0.0.0 \
    NOTEBOOK_PORT=8888  

#  In china  change the sources.list well speed up when you download files 
COPY ./config /tmp/
RUN apt-get update -qqy &&  apt-get install ca-certificates -y
    #  change the sources.list 
RUN mv /tmp/sources.list /etc/apt/sources.list  && \
    apt-get update -qqy  && \
    apt-get install -y wget bzip2 libglib2.0-0 libxext6 libsm6 libxrender1 git mercurial subversion vim && \
    apt-get clean


RUN wget --quiet https://repo.anaconda.com/archive/Anaconda3-2019.10-Linux-x86_64.sh -O ~/anaconda.sh  && \
    /bin/bash ~/anaconda.sh -b -p /opt/conda && \
    rm -rf  ~/anaconda.sh  && \
    ln -s /opt/conda/etc/profile.d/conda.sh /etc/profile.d/conda.sh && \
    echo ". /opt/conda/etc/profile.d/conda.sh" >> ~/.bashrc && \
    echo "conda activate base" >> ~/.bashrc && \
    # set pip sources 
    pip config set global.index-url https://mirrors.aliyun.com/pypi/simple/ && \
    # or 
    # mv  /tmp/pip.conf ~/.config/pip/pip.conf
    mv /tmp/.condarc ~/.condarc && \
    # clean
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

CMD jupyter notebook \
	--notebook-dir=${NOTEBOOK_DIR} \
	--ip=${NOTEBOOK_IP} \
	--port=${NOTEBOOK_PORT} \
	--NotebookApp.token='' \
	--no-browser \
	--allow-root
