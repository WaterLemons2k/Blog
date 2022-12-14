---
layout: post
title: Windows搭建NTP服务器
---
# 安装

1.  下载NetTime 3.14  (**仅支持IPv4**) [下载地址1](http://timesynctool.com/NetTimeSetup-314.exe) [下载地址2](https://file.waterlemons2k.com/NetTimeSetup-314.exe) [下载地址3](https://archive.org/download/NetTimeSetup/NetTimeSetup-314.exe)
2.  运行安装程序，点击`Next`  
![setup](/assets/Windows-NTP-Server/setup.png)
3.  选择安装位置。点击`Next`  
![Location](/assets/Windows-NTP-Server/Location.png)
4.  选择开始菜单文件夹，点击`Next`  
![Folder](/assets/Windows-NTP-Server/Folder.png)
5.  选择要添加的任务，勾选`Install as Service (Recommended)`点击Next  
![Task](/assets/Windows-NTP-Server/Task.png)
6.  准备开始安装，点击`Install`  
![Install](/assets/Windows-NTP-Server/Install.png)
7.  点击`Finish`完成安装  
![Finish](/assets/Windows-NTP-Server/Finish.png)

# 配置NetTime

1.  找到任务栏托盘处的NetTime 图标，如下图所示:  
![Icon](/assets/Windows-NTP-Server/Icon.png)
2.  单击`NetTime`图标，在弹出的`Network Time`窗口中点击`Settings...`如下图所示:  
![Window](/assets/Windows-NTP-Server/Window.png)
3.  在弹出的`NetTime Options`窗口中勾选`Allow other computers to sync to this computer`，取消勾选`Automatically Check For Updates every 7 day(s)`，点击`OK`，如下图所示:  
![Options](/assets/Windows-NTP-Server/Options.png)

# 设置防火墙

安装NetTime后并不会自动开放NTP需要的UDP协议123端口，您需要以管理员身份运行:
```
netsh firewall add portopening UDP 123 "123UDP"
```
完成!