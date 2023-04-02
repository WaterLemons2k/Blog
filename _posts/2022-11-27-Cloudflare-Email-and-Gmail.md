---
layout: post
title: 使用Cloudflare 电子邮件路由和Gmail收发邮件
---

[Cloudflare 电子邮件路由](https://www.cloudflare.com/zh-cn/products/email-routing) 可以将个人域名的邮箱转发至其它邮箱，本文我们通过 Gmail 做到使用个人域名收发邮件。

# Cloudflare 接收邮件
1. 请确保已在 Cloudflare 上添加了用于收发邮件的站点（没有请看 [Cloudflare添加站点](Cloudflare-add-site)），然后点击 `电子邮件` -> `开始使用`：

   ![Start](/assets/Cloudflare-Email-and-Gmail/Start.png)

2. 在 `自定义地址` 栏输入邮箱前缀，`目标地址` 栏输入 Gmail 地址，点击 `创建并继续`：

   ![Create-custom-address](/assets/Cloudflare-Email-and-Gmail/Create-custom-address.png)

3. 如果是新地址则会收到 `验证电子邮件路由地址` 邮件，点击 `验证电子邮箱地址`，验证成功后会提示 `启用电子邮件路由`，点击 `添加记录并启用`：

   ![Enable-email-routing](/assets/Cloudflare-Email-and-Gmail/Enable-email-routing.png)

4. 当显示 `配置摘要` 时，完成！

   ![Configuration-summary](/assets/Cloudflare-Email-and-Gmail/Configuration-summary.png)

# Gmail 发送邮件
1. 接下来使用 [应用专用密码](https://myaccount.google.com/apppasswords) 为 Gmail 生成一个密码。

   在 `选择应用` 列中选择 `其它（自定义名称）`，填一个好记的名字（例如邮箱前缀），点击 `生成`：

   ![apppasswords](/assets/Cloudflare-Email-and-Gmail/apppasswords.png)

2. 保存黄框中的 `应用专用密码`，点击 `完成`：

   ![apppasswords-generated](/assets/Cloudflare-Email-and-Gmail/apppasswords-generated.png)

3. 打开 Gmail，点击 `设置` -> `查看所有设置` -> [`账号和导入`](https://mail.google.com/mail/#settings/accounts) -> `用这个地址发送邮件：` -> `添加其他电子邮件地址`：

   ![Add-another-email](/assets/Cloudflare-Email-and-Gmail/Add-another-email.png)

4. 此时会弹出一个新窗口，在 `名称：` 行输入邮箱的名称（**会对外展示，请慎重填写**），在 `电子邮件地址：` 行输入 Cloudflare 中添加的邮箱地址（请提前确认可以接收邮件），点击下一步，如下图所示：

   ![Add-another-email-window1](/assets/Cloudflare-Email-and-Gmail/Add-another-email-window1.png)

5. 接下来会提示 `通过SMTP服务器发送邮件`，在 `SMTP服务器：` 行输入`smtp.gmail.com`，`用户名` 行输入 Gmail 的用户名（邮箱不带 `@gmail.com`），`密码` 行输入之前保存的 `应用专用密码`，最后点击 `添加帐号 »`：

   ![Add-another-email-window2](/assets/Cloudflare-Email-and-Gmail/Add-another-email-window2.png)

6. 如果配置无误，Gmail 会受到一封邮件，填入邮件的确认代码并点击 `验证`：

   ![Add-another-email-window3](/assets/Cloudflare-Email-and-Gmail/Add-another-email-window3.png)

完成！

引用：https://blog.shuziyimin.org/1355