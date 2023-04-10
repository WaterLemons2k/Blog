---
title: Alpine Linux 安装 Docker
date: 2022-10-08
---

1. 由于 Alpine Linux 只有社区源中才有 Docker，所以我们需要导入社区源
```
echo "http://dl-cdn.alpinelinux.org/alpine/latest-stable/community" >> /etc/apk/repositories
```
2. 更新源并安装 Docker
```
apk add -U docker
```
3. 将 Docker 添加到开机启动项
```
rc-update add docker boot
```
4. 启动 Docker 服务
```
service docker start
```
5. 查看 Docker 版本
```
docker -v
```

相关文章：
- [Docker 删除未使用的数据](/docker-system-prune)
- [Docker 构建多架构镜像](/Docker-multi-arch)

完成！  
引用：https://cloud.tencent.com/developer/article/1834837