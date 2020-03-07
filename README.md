# 常用Linux Docker镜像 国内加速版

在国内使用使用 docker 时，常因为墙的原因，下载速度很慢，甚至出现连接中断情况，导致镜像构建失败。

解决办法之一就是 将基础操作系统镜像的下载源修改为国内镜像源，实现进行加速。

正因为如此，我统一构建了常用的 linux 镜像中的源为 国内[清华大学的镜像源](https://mirror.tuna.tsinghua.edu.cn/)。具体如下：

[ubuntu](https://hub.docker.com/repository/docker/mengkevin/ubuntu)、[debian](https://hub.docker.com/repository/docker/mengkevin/debian)、[python](https://hub.docker.com/repository/docker/mengkevin/python)、[anaconda](https://hub.docker.com/repository/docker/mengkevin/anaconda)


## 1. Ubuntu

Ubuntu 提供四个修改为清华源后的镜像版本[dockerhub](https://hub.docker.com/repository/docker/mengkevin/ubuntu)：
- a. Ubuntu 18.04：`ubuntu：18.04`
- b. Ubuntu 16.04：`ubuntu：16.04`
- c. Ubuntu 14.04：`ubuntu：14.04`
- d. Ubuntu 12.04：`ubuntu：12.04`

## 2. Debian
Debian 提供四个修改为清华源后的镜像版本 [dockerhub](https://hub.docker.com/repository/docker/mengkevin/debian)：
- a. Debian10-buster：`debian：buster`；
- b. Debian10-buster-slim：`debian：buster-slim`；
- c. Debian9-stretch：`debian：stretch`；`
- d. Debian9-stretch-slim：`debian：stretch-slim`；`



## 3. CentOS

CentOS 在安装时会自动选择速度最快的镜像位置下载，所以无需加速。：）

``` bash
[root@df1663587f34 /]# yum install wget
Loaded plugins: fastestmirror, ovl
Determining fastest mirrors
 * base: ftp.sjtu.edu.cn
 * extras: mirrors.163.com
 * updates: ftp.sjtu.edu.cn
```

## 4. Python

python 提供11个修改为`清华源`后的镜像版本、以及`pip阿里云`镜像版本[dockerhub](https://hub.docker.com/repository/docker/mengkevin/python)：
- a. python 2.7： `2.7-slim-buster`；`2.7-buster`；
- b. python 3.9： `3.9-rc-buster`；
- c. python 3.8： `3.8-slim-buster`；`3.8-buster`；
- d. python 3.7： `3.7-slim-buster`；`3.7-buster`；
- e. python 3.6： `3.6-slim-buster`；`3.6-buster`；
- f. python 3.5： `3.5-slim-buster`；`3.5-buster`；


## 5. Anaconda

anaconda 提供1个修改为`清华源`后的镜像版本、`pip阿里云`镜像和`conda 清华镜像`版本 [dockerhub](https://hub.docker.com/repository/docker/mengkevin/anaconda)：
- a. 对应 `Anaconda3-2019.10-Linux-x86_64` 版本。 标签：`2019`



## 构建与测试
构建与测试方法如下：
### 构建
```bash
cd 18.04 LTS
docker build -t mengkevin/ubuntu:18.04 .
```

### 测试
```bash
docker run --name test -it --rm  mengkevin/ubuntu:18.04
```

### anaconda 启动
```bash
docker run -v $(pwd):/src/notebooks -p 8888:8888 -td mengkevin/anaconda:201910
```