---
layout: post
title: Docker 构建多架构镜像
---

# 安装 buildx
如果需要构建多架构的 Docker 镜像，可以使用在 Docker 19.03 中引入的 `buildx` 命令：
```
docker buildx
```
如果出现下列错误，代表 `buildx` 还未安装：
```
docker: 'buildx' is not a docker command.
See 'docker --help'
```
为 Alpine Linux 安装 `buildx`：
```
apk add docker-cli-buildx
```
# 配置 buildx
安装 QEMU 模拟器：
```
docker run --privileged --rm tonistiigi/binfmt --install all
```
创建 builder 实例：
```
docker buildx create --use
```
# 构建 Docker 镜像
在当前目录创建 `Dockerfile` 文件，以下是示例：
```Dockerfile
FROM busybox:uclibc
ARG TARGETARCH
RUN echo "I'm building for $TARGETARCH"
```
此示例 `Dockerfile` 文件声明基础镜像是 `busybox:uclibc`，声明架构变量 `TARGETARCH`，在构建时输出构建的架构  
有关更多架构变量，请见：[Dockerfile reference | Docker Documentation](https://docs.docker.com/engine/reference/builder/#automatic-platform-args-in-the-global-scope)

使用 `buildx` 命令构建架构为 `amd64`、`arm`、`arm64`，标签为 `arch` 的镜像：
```
docker buildx build --platform amd64,arm,arm64 -t arch .
```
输出：
```
WARN[0000] No output specified for docker-container driver. Build result will only remain in the build cache. To push result image into registry use --push or to load image into docker use --load 
[+] Building 13.8s (12/12) FINISHED
 => [internal] booting buildkit 5.3s
 => => pulling image moby/buildkit:buildx-stable-1 2.2s
 => => creating container buildx_buildkit_dazzling_noyce0 3.1s
 => [internal] load build definition from Dockerfile 0.0s
 => => transferring dockerfile: 112B 0.0s
 => [internal] load .dockerignore 0.0s
 => => transferring context: 2B 0.0s
 => [linux/amd64 internal] load metadata for docker.io/library/busybox:uclibc 6.4s
 => [linux/arm64 internal] load metadata for docker.io/library/busybox:uclibc 6.4s
 => [linux/arm/v7 internal] load metadata for docker.io/library/busybox:uclibc 6.4s
 => [linux/arm64 1/2] FROM docker.io/library/busybox:uclibc@sha256:133c96e963fb798875f6dd48df3fd6e5d474e28b6f90cebef4f49f5b416200db  0.2s
 => => resolve docker.io/library/busybox:uclibc@sha256:133c96e963fb798875f6dd48df3fd6e5d474e28b6f90cebef4f49f5b416200db 0.0s
 => => sha256:9836d7c303877b21ce6157ef5e9a05f8d57ce86e8a1dc672777f6bbdbce6e9e3 833.12kB / 833.12kB 1.3s
 => => extracting sha256:9836d7c303877b21ce6157ef5e9a05f8d57ce86e8a1dc672777f6bbdbce6e9e3 0.2s
 => [linux/amd64 1/2] FROM docker.io/library/busybox:uclibc@sha256:133c96e963fb798875f6dd48df3fd6e5d474e28b6f90cebef4f49f5b416200db 0.2s
 => => resolve docker.io/library/busybox:uclibc@sha256:133c96e963fb798875f6dd48df3fd6e5d474e28b6f90cebef4f49f5b416200db 0.0s
 => => sha256:4399114b4c59be45238d2958ccaef1fa50ac18f83d2c1bb585e15a4af273b31f 778.68kB / 778.68kB 1.5s
 => => extracting sha256:4399114b4c59be45238d2958ccaef1fa50ac18f83d2c1bb585e15a4af273b31f 0.2s
 => [linux/arm/v7 1/2] FROM docker.io/library/busybox:uclibc@sha256:133c96e963fb798875f6dd48df3fd6e5d474e28b6f90cebef4f49f5b416200db 0.1s
 => => resolve docker.io/library/busybox:uclibc@sha256:133c96e963fb798875f6dd48df3fd6e5d474e28b6f90cebef4f49f5b416200db 0.0s
 => => sha256:385e4e16fa93807eb4867a8f553c32d6eb1f0275822b84a047342bb42e7cba66 729.12kB / 729.12kB 1.2s
 => => extracting sha256:385e4e16fa93807eb4867a8f553c32d6eb1f0275822b84a047342bb42e7cba66 0.1s
 => [linux/arm/v7 2/2] RUN echo "I'm building for arm" 0.3s
 => [linux/arm64 2/2] RUN echo "I'm building for arm64" 0.3s
 => [linux/amd64 2/2] RUN echo "I'm building for amd64" 0.2s
 ```
添加 `--push` 选项以将 Docker 镜像推送到 Docker Hub：
```
docker buildx build --push --platform amd64,arm,arm64 -t arch .
```
添加 `--load` 选项以将 Docker 镜像保存到本地（此选项仅支持同时构建 1 种架构）：
```
docker buildx build --load --platform amd64 -t arch . 
```

相关文章：
- [Alpine Linux安装Docker](Alpine-add-docker)
- [Docker 删除未使用的数据](docker-system-prune)

参考：
1. [docker buildx - Docker Documentation](https://docs.docker.com/engine/reference/commandline/buildx/)
2. [Multi-platform images - Docker Documentation](https://docs.docker.com/build/building/multi-platform/)
3. [Dockerfile reference - Docker Documentation](https://docs.docker.com/engine/reference/builder/)
4. [Install Docker Buildx - Docker Documentation](https://docs.docker.com/build/install-buildx/)
5. [tonistiigi/binfmt: Cross-platform emulator collection distributed with Docker images.](https://github.com/tonistiigi/binfmt)
6. [使用 buildx 构建多种系统架构支持的 Docker 镜像 - Docker — 从入门到实践](https://yeasy.gitbook.io/docker_practice/buildx/multi-arch-images)
7. [Alpine Linux packages](https://pkgs.alpinelinux.org/package/edge/community/x86/docker-cli-buildx)