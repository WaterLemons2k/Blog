---
title: 使用Gridea在GitHub Pages上搭建博客
date: 2022-06-07
---

引用:https://gridea.dev/gridea-start/

1.  首先点击[这里](https://gridea.dev/#started)下载 Gridea,然后点击[这里](https://github.com/settings/tokens/new)创建 Token.
2.  在 Note 栏填入名称，将 Expiration(过期时间)设为 No expiration(无限制),最后点 Generate token,记下 Token.如下图所示:  
    ![Token](/Gridea-on-GitHub-Pages/Token.png)
3.  创建一个仓库。在 Repository Name 栏填入`user.github.io`(将`user`替换为`GitHub用户名`),将状态设为 Public(公开)，点击`Create repository`  
    ![repo](/Other/GitHub-Create-repository.png)
4.  打开 Gridea,平台设置为 Github Pages,在域名栏填入 user.github.io(或在域名和 CNAME 栏填入自定义域名),如下图所示:，然后点击检测远程连接检查，检查成功后保存。  
    ![Gridea](/Gridea-on-GitHub-Pages/Gridea.png)
5.  点击同步后等几分钟，如果访问失败请回到存放 Gridea 的仓库，点 Settings(设置)-Pages,将 Source(来源)设置为 main,点击 Save(保存).保存后再次尝试同步。
    ![Pages](/Gridea-on-GitHub-Pages/Pages.png)

完成!  
相关博客:[Gridea 使用 Gitalk 评论系统](/gridea-gitalk)
