---
title: Windows搭建NTP服务器
date: 2022-07-29
---

# 安装

1.  下载 NetTime 3.14 (**仅支持 IPv4**) [下载地址 1](http://timesynctool.com/NetTimeSetup-314.exe) [下载地址 2](https://file.waterlemons2k.com/NetTimeSetup-314.exe) [下载地址 3](https://archive.org/download/NetTimeSetup/NetTimeSetup-314.exe)
2.  运行安装程序，点击`Next`  
    ![setup](/Windows-NTP-Server/setup.png)
3.  选择安装位置。点击`Next`  
    ![Location](/Windows-NTP-Server/Location.png)
4.  选择开始菜单文件夹，点击`Next`  
    ![Folder](/Windows-NTP-Server/Folder.png)
5.  选择要添加的任务，勾选`Install as Service (Recommended)`点击 Next  
    ![Task](/Windows-NTP-Server/Task.png)
6.  准备开始安装，点击`Install`  
    ![Install](/Windows-NTP-Server/Install.png)
7.  点击`Finish`完成安装  
    ![Finish](/Windows-NTP-Server/Finish.png)

# 配置 NetTime

1.  找到任务栏托盘处的 NetTime 图标，如下图所示:  
    ![Icon](/Windows-NTP-Server/Icon.png)
2.  单击`NetTime`图标，在弹出的`Network Time`窗口中点击`Settings...`如下图所示:  
    ![Window](/Windows-NTP-Server/Window.png)
3.  在弹出的`NetTime Options`窗口中勾选`Allow other computers to sync to this computer`，取消勾选`Automatically Check For Updates every 7 day(s)`，点击`OK`，如下图所示:  
    ![Options](/Windows-NTP-Server/Options.png)

# 设置防火墙

安装 NetTime 后并不会自动开放 NTP 需要的 UDP 协议 123 端口，您需要以管理员身份运行:

```
netsh firewall add portopening UDP 123 "123UDP"
```

完成!
