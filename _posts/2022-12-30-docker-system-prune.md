---
layout: post
title: Docker 删除未使用的数据
---

如果需要 Docker 删除未使用的数据，可以运行下列命令：
```
docker system prune
```
运行后会出现**警告**：
```
WARNING! This will remove:
  - all stopped containers
  - all networks not used by at least one container
  - all dangling images
  - all dangling build cache

Are you sure you want to continue? [y/N] 
```
输入 `y` 并按回车以继续。

相关文章：
- [Alpine Linux安装Docker](Alpine-add-docker)
- [Docker 构建多架构镜像](Docker-multi-arch)

参考：
1. [How to remove &lt;none&gt; images after building - DockerEngine - Docker Community Forums](https://forums.docker.com/t/how-to-remove-none-images-after-building/7050)
2. [docker system prune - Docker Documentation](https://docs.docker.com/engine/reference/commandline/system_prune/)