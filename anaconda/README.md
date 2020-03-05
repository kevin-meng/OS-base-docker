# Anaconda Using in China
build this image  in order to be more friendly for people in China。
the main changes as below

1. using Tunghua Unviersity mirror replace the default sources.list   
2. using the ALiyun mirror for the pip 
3. using the Tunghua Unviersity mirror for the conda


## build the image
```bash
docker build -t anacond:latest .
```

## run the image
```bash
docker run -v $(pwd):/src/notebooks -p 8888:8888 -td anacond:latest
```

# Anaconda 镜像中国化
通过这个镜像，对中国的用户更友好。通过下面三项变化，加速国内安装软件或 Python 包的速度。

1. 用清华源替换系统源 
2. 用阿里云的 pip 镜像 替换默认
3. 用清华 conda 源替换默认

