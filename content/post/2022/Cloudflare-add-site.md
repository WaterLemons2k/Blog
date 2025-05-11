---
title: Cloudflare添加站点
date: 2022-11-26
---

1. 首先[登录 Cloudflare](https://dash.cloudflare.com)，将语言从`English (US)`切换为`简体中文`，然后点击右上角的`添加站点`，在`输入您的站点 (example.com)：`框中输入你的域名，点击蓝色的`添加站点`，如下图所示：
   ![Add-site](/Cloudflare-add-site/Add-site.png)
2. 选择`Free`(免费)套餐，点击继续，如下图所示：
   ![Step-1](/Cloudflare-add-site/Step-1.png)
3. 提示添加 DNS 记录，点击继续，如下图所示：
   ![Step-2](/Cloudflare-add-site/Step-2.png)
4. 弹窗提示立即设置 DNS 记录，这里不添加，点击确认，如下图所示：
   ![Step-2-Pop-up](/Cloudflare-add-site/Step-2-Pop-up.png)
5. 提示更改名称服务器，请根据提示到您的域名注册机构将`NS记录`更改为`Cloudflare 名称服务器`，点击`完成，检查名称服务器`，如下图所示：
   ![Step-3](/Cloudflare-add-site/Step-3.png)
6. 接下来会跳转至快速入门指南，这里点击`开始使用`，按照提示完成，如下图所示：
   ![Quick-start-guide](/Cloudflare-add-site/Quick-start-guide.png)
7. 等待最长 24 小时后再次查看，如果出现下图表示成功：
   ![Finish](/Cloudflare-add-site/Finish.png)
