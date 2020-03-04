## 介绍

Ubuntu 提供四个修改为清华源后的镜像版本：
1. Ubuntu 18.04
2. Ubuntu 16.04
3. Ubuntu 14.04
4. Ubuntu 12.04


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
