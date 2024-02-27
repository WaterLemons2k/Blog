---
title: VMware使用USB输入设备
date: 2022-03-06
---

将 USB 输入设备(如 USB 键盘)连接到 VMware Workstation 时，可能会出现  
![error](/Other/VMware-HID-error.png)  
这时，在虚拟机的.vmx 配置文件里添加一行即可解决

```
usb.generic.allowLastHID = "TRUE"
```

参考:https://blog.csdn.net/future_ai/article/details/80603724
