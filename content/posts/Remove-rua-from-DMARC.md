---
title: 停止接收 DMARC 的报告邮件 - 移除 `rua` 标签
date: 2023-03-24
---

起因是我收到了来自 [`DMARC Aggregate Report`](mailto:dmarcreport@microsoft.com) 的报告邮件：

```
This is a DMARC aggregate report from Microsoft Corporation. For Emails received between ****-**-** 00:00:00 UTC to ****-**-** 00:00:00 UTC.

You're receiving this email because you have included your email address in the 'rua' tag of your DMARC record in DNS for ****.com. Please remove your email address from the 'rua' tag if you don't want to receive this email.
```

如果不想收到 DMARC 的报告邮件，可以通过移除 `rua` 标签来停止接收，步骤如下：

1. 登录到邮箱的域名服务商。
2. 找到名称为 `_dmarc` 的 DNS TXT 记录，示例：
   ```
   v=DMARC1; p=quarantine; rua=mailto:name@example.com
   ```
3. 移除 `rua` 标签，像这样：
   ```
   v=DMARC1; p=quarantine
   ```
4. 保存。

参考：
1. [Email server: Remove rua from DMARC DNS entry or stop receiving DMARC reports - Server Fault](https://serverfault.com/questions/988556/email-server-remove-rua-from-dmarc-dns-entry-or-stop-receiving-dmarc-reports)
2. [RFC 7489: Domain-based Message Authentication, Reporting, and Conformance (DMARC)](https://www.rfc-editor.org/rfc/rfc7489#page-19)