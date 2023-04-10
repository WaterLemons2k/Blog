---
title: 缩小.img镜像
date: 2022-07-01
---

创建.img镜像时，镜像末尾可能会有大量空闲空间，但可以删除

1.运行`fdisk -l .img`(将`.img`替换为`要缩小的镜像文件`)查看镜像信息，如下面所示:

```

fdisk -l .img
Disk .img: 5 GiB, 5368709120 bytes, 10485760 sectors
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disklabel type: gpt
Disk identifier: 9A3068F9-8DB8-BFCC-01C406213F67
    
Device       Start     End Sectors  Size  Type
.img1        2048 4982527 4980480  2.4G  Linux
.img2      4982528 9176831 4194304  2G  Linux

```

2.将`End`(末尾)行的最后一列(示例为`9176831`)替换到下列命令的`End`处,将`镜像文件`替换到`.img`处，如下行所示：

```
truncate --size=$[(End+1)*512] .img
```

替换后：

```
truncate --size=$[(9176831+1)*512] .img
```

完成!

引用:https://binac.io/posts/shrink-disk-image/