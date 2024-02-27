---
title: 使用GitHub Pages和Minima搭建博客
date: 2022-11-25
---

使用 GitHub Pages 和 Jeykll 的[Minima](https://github.com/jekyll/minima)主题搭建博客

1. 首先点击[这里](http://github.com/new)在 GitHub 上创建一个仓库(需要登录)，在`Repository name`栏填入仓库名称`user.github.io`(将`user`替换为你的`GitHub用户名`)，点击`Create repository`
   ![repo](/Other/GitHub-Create-repository.png)
2. 点击`creating a new file`，在`Name your file...`栏输入`_config.yml`来创建 Jekyll 配置文件，在`Edit new file`处输入:

```
theme: minima
```

输入完成后，点击`Commit new file`提交文件

3. 点击`Add file` -> `Create new file`，这次在`Name your file...`栏输入`index.md`来创建博客首页，在`Edit new file`处输入:

```
---
layout: home
---
```

输入完成后，点击`Commit new file`提交文件

4. 再次点击`Add file` -> `Create new file`，这次在`Name your file...`栏输入`_posts/2022-11-25-Hello-World.md`来创建第一篇文章

- `_posts/` : 文件在`_posts`目录中
- `2022-11-25` : 日期
- `Hello-World` : 文章文件名

在`Edit new file`处先输入:

```
---
layout: post
title: 你好世界
---
```

- `layout: post` : 表明此文件是一篇文章
- `title: 你好世界` : 表明此文章的标题是你好世界，可以任意更改

接下来就可以使用[Markdown](https://markdown.com.cn)开始撰写文章了！输入完成后，点击`Commit new file`提交文件

5.全部完成后，就可以使用`GitHub Pages`开始搭建博客了！点击`Settings`(设置) -> `Pages`，将`Branch`(分支)设为`main`(主要) ,点击`Save`保存，如图所示：
![Pages](/Minima-on-GitHub-Pages/Pages.png) 6.保存后等几分钟，点击`Actions`，出现绿色的对勾![passed](/Other/passed.svg)表示构建成功，点击`Workflow` -> `deploy`框中出现的蓝色网址即可打开博客，如图所示：
![Actions](/Minima-on-GitHub-Pages/Actions.png)

完成！
