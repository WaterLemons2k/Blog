---
layout: post
title: Alpine Linux安装Docker
---
1. 首先，由于Alpine Linux只有社区源中才有Docker，所以我们需要导入社区源  
`echo "http://dl-cdn.alpinelinux.org/alpine/latest-stable/community" >>/etc/apk/repositories`
2. 更新源并安装Docker  
`apk add -U docker`
3. 设置开机启动Docker  
`rc-update add docker boot`
4. 启动Docker服务  
`service docker start`
5. 查看Docker版本  
`docker -v`

完成！  
引用：https://cloud.tencent.com/developer/article/1834837