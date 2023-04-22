---
title: Gridea使用Gitalk评论系统
date: 2022-06-07
---

引用:https://xgmm.me/post/gridea-pei-zhi-gitalk-ping-lun-xi-tong/  
这是一个如何在Gridea里使用Gitalk的教程  
[Gridea配置教程](https://gridea.dev/gridea-start/)
# 配置OAuth
首先，在[这里](https://github.com/settings/applications/new)配置OAuth application  
![OAuth](/gridea-gitalk/OAuth.png)  
点击Register application.记下Client ID，然后点击Generate a new client secret  
![Generate](/gridea-gitalk/Generate.png)  
记下Cleient secrets
# 配置Gridea
打开Gridea,点击远程-评论配置，配置如图  
![Gridea](/gridea-gitalk/Gridea.png)  
配置完成后点击同步，然后使用Homepage URL里的地址访问。随便打开一篇文章滑到最底部，你会看到:

![bind](/gridea-gitalk/bind.png)  
点击使用 GitHub 登录，然后点击Authorize来授权  
![Authorize](/gridea-gitalk/Authorize.png)  
完成!  
相关博客:[使用Gridea在GitHub Pages上搭建博客](/Gridea-on-GitHub-Pages)