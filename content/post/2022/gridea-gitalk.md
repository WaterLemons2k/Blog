---
title: Gridea使用Gitalk评论系统
date: 2022-06-07
---

引用:https://xgmm.me/post/gridea-pei-zhi-gitalk-ping-lun-xi-tong/  
这是一个如何在 Gridea 里使用 Gitalk 的教程  
[Gridea 配置教程](https://gridea.dev/gridea-start/)

# 配置 OAuth

首先，在[这里](https://github.com/settings/applications/new)配置 OAuth application  
![OAuth](/gridea-gitalk/OAuth.png)  
点击 Register application.记下 Client ID，然后点击 Generate a new client secret  
![Generate](/gridea-gitalk/Generate.png)  
记下 Cleient secrets

# 配置 Gridea

打开 Gridea,点击远程-评论配置，配置如图  
![Gridea](/gridea-gitalk/Gridea.png)  
配置完成后点击同步，然后使用 Homepage URL 里的地址访问。随便打开一篇文章滑到最底部，你会看到:

![bind](/gridea-gitalk/bind.png)  
点击使用 GitHub 登录，然后点击 Authorize 来授权  
![Authorize](/gridea-gitalk/Authorize.png)  
完成!  
相关博客:[使用 Gridea 在 GitHub Pages 上搭建博客](/Gridea-on-GitHub-Pages)
