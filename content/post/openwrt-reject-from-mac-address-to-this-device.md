---
title: OpenWrt 拒绝指定 MAC 地址连接到此设备
date: 2023-06-28
---

有时您可能会需要让指定设备无法连接到外网。如果指定设备的 DHCP 服务器和 DNS 服务器都位于某台 OpenWrt 设备上，便可以通过 **拒绝指定 MAC 地址连接到此 OpenWrt 设备** 来做到这一点：

1. 登录到 OpenWrt 的 LuCI 网页界面，然后转到 `网络` -> `防火墙` -> `通信规则`：

   ![通信规则](/openwrt-reject-from-mac-address-to-this-device/traffic-rules.png)

2. 点击 `添加`：

   - `源区域` 选择 `lan`
   - `目标区域` 选择 `设备 (输入)`
   - `操作` 选择 `拒绝`

   ![通信规则 - 通用设置](/openwrt-reject-from-mac-address-to-this-device/general-settings.png)

3. 然后点击 `高级设置`，在 `源 MAC 地址` 处添加要拒绝的 MAC 地址。完成后点击 `保存` -> `保存并应用`。

   ![通信规则 - 高级设置](/openwrt-reject-from-mac-address-to-this-device/advanced-settings.png)

此时被拒绝的 MAC 地址便无法再访问此 OpenWrt 设备了（包括 DHCP 服务器和 DNS 服务器）。

参考：

1. [请问各位大佬 OPENWRT，如何设置 MAC 过滤？-OPENWRT 专版-恩山无线论坛 - Powered by Discuz!](https://www.right.com.cn/forum/thread-4031773-1-1.html)
2. [如何禁止电视的 IP 通过 wan 口联网?-OPENWRT 专版-恩山无线论坛 - Powered by Discuz!](https://www.right.com.cn/forum/thread-8275165-1-1.html)
