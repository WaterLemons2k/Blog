---
layout: post
title: 使用Cloudflare 电子邮件路由和Gmail收发邮件
---

[Cloudflare 电子邮件路由](https://www.cloudflare.com/zh-cn/products/email-routing)可以将个人域名邮箱转发至其它邮箱，本文我们搭配`Gmail`做到使用个人域名收发邮件

# Cloudflare 接收邮件
1.首先请确保已在Cloudflare上添加站点（如果没有请看 [Cloudflare添加站点](Cloudflare-add-site)），然后点击`电子邮件` -> `开始使用`，如下图所示：

![Start](/assets/Cloudflare-Email-and-Gmail/Start.png)

2.在`自定义地址`栏输入`邮箱前缀`，`目标地址`栏输入`Gmail地址`，点击`创建并继续`，如下图所示：

![Create-custom-address](/assets/Cloudflare-Email-and-Gmail/Create-custom-address.png)

3.你会收到一封`验证电子邮件路由地址`邮件，点击`验证电子邮箱地址`，验证成功后会提示`启用电子邮件路由`，点击`添加记录并启用`，如下图所示：

![Enable-email-routing](/assets/Cloudflare-Email-and-Gmail/Enable-email-routing.png)

4.当`配置摘要`如下图所示时，完成！

![Configuration-summary](/assets/Cloudflare-Email-and-Gmail/Configuration-summary.png)

# Gmail 发送邮件
1.点击[应用专用密码](https://myaccount.google.com/apppasswords)，在`选择应用`列中选择`其它（自定义名称）`，填一个好记的名字，点击`生成`，如下图所示：

![apppasswords](/assets/Cloudflare-Email-and-Gmail/apppasswords.png)

2.复制黄框中的`应用专用密码`，如下图所示：

![apppasswords-generated](/assets/Cloudflare-Email-and-Gmail/apppasswords-generated.png)

3.打开[Gmail](https://mail.google.com/mail)，点击`设置` -> `查看所有设置` -> [账号和导入](https://mail.google.com/mail/#settings/accounts)，在`用这个地址发送邮件：`栏中点击`添加其他电子邮件地址`，如下图所示：

![Add-another-email](/assets/Cloudflare-Email-and-Gmail/Add-another-email.png)

4.出现一个弹窗，在`名称：`行输入邮箱的名称（**会对外展示，请慎重填写**），在`电子邮件地址：`行输入Cloudflare中添加的邮箱地址（请提前确认可以接收邮件），点击下一步，如下图所示：

![Add-another-email-window1](/assets/Cloudflare-Email-and-Gmail/Add-another-email-window1.png)

5.接下来提示通过SMTP服务器发送邮件，在`SMTP服务器：`行输入`smtp.gmail.com`，`用户名`行输入`Gmail用户名`，`密码`行输入之前获取的`应用专用密码`，点击`添加帐号 »`，如下图所示：

![Add-another-email-window2](/assets/Cloudflare-Email-and-Gmail/Add-another-email-window2.png)

6.如果配置无误，Gmail会受到一封邮件，填入邮件的确认代码并点击`验证`，如下图所示：

![Add-another-email-window3](/assets/Cloudflare-Email-and-Gmail/Add-another-email-window3.png)

完成！

引用：https://blog.shuziyimin.org/1355