


## 介绍

这里提供四个修改为清华源后的镜像版本：
1. Debian10-buster
2. Debian10-buster-slim
3. Debian9-stretch
4. Debian9-stretch-slim


## 构建与测试
构建与测试方法如下：
### 构建
```bash
cd Debian9-stretch-slim
docker build -t mengkevin/debian:stretch-slim .
```

### 测试
```bash
docker run --name test -it --rm  mengkevin/debian:stretch-slim
```



##  Debian 发行版目录
- 下一代 Debian 正式发行版的代号为 bullseye — 发布时间尚未确定
- Debian 10（buster） — 当前的稳定版（stable）
- Debian 9（stretch） — 旧的稳定版（oldstable）
- Debian 8（jessie） — 更旧的稳定版（oldoldstable）
- Debian 7（wheezy） — 被淘汰的稳定版
- Debian 6.0（squeeze） — 被淘汰的稳定版
- Debian GNU/Linux 5.0（lenny） — 被淘汰的稳定版
- Debian GNU/Linux 4.0（etch） — 被淘汰的稳定版
- Debian GNU/Linux 3.1（sarge） — 被淘汰的稳定版
- Debian GNU/Linux 3.0（woody） — 被淘汰的稳定版
- Debian GNU/Linux 2.2（potato） — 被淘汰的稳定版
- Debian GNU/Linux 2.1（slink） — 被淘汰的稳定版
- Debian GNU/Linux 2.0（hamm） — 被淘汰的稳定版

## 参考 reference
https://www.debian.org/releases/