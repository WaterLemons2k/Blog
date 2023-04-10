---
title: VMware使用USB输入设备
date: 2022-03-06
---

将USB输入设备(如USB键盘)连接到VMware Workstation时，可能会出现  
![error](/Other/VMware-HID-error.png)  
这时，在虚拟机的.vmx配置文件里添加一行即可解决
```
usb.generic.allowLastHID = "TRUE"
```
参考:https://blog.csdn.net/future_ai/article/details/80603724