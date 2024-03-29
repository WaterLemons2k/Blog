---
title: ESXi使用RDM直通硬盘
date: 2022-03-13
---

引用: https://www.77bx.com/60.html

1.登录 ESXi，点击`操作` -> `服务` -> `启用安全 Shell (SSH)`  
![EnableSSH](/ESXi-RDM/EnableSSH.png)

2.点击`存储` -> `设备`，找到 `硬盘` 名称括号里的内容（本文为`t10.ATA______VMware_Virtual_SATA_Hard_Drive___________00000000000000000001`）
![disk](/ESXi-RDM/disk.png)

3.点击`存储` -> `数据存储`，找到 `数据存储` 名称（本文为`datastore1`）
![datastore](/ESXi-RDM/datastore.png)

4.连接到 ESXi 的 SSH，然后执行:

```
vmkfstools -z /vmfs/devices/disks/<硬盘> /vmfs/volumes/<数据存储>/<名称>.vmdk
```

示例:

```
vmkfstools -z /vmfs/devices/disks/t10.ATA______VMware_Virtual_SATA_Hard_Drive___________00000000000000000001 /vmfs/volumes/datastore1/1.vmdk
```

5.回到 `数据存储` 里检查一下  
![file](/ESXi-RDM/file.png)  
完成!
