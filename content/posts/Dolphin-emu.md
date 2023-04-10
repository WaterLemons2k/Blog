---
title: Dolphin模拟器使用教程
date: 2022-03-06
---

首先请[下载](https://cn.dolphin-emu.org/)Dolphin模拟器，[备用下载](https://file.waterlemons2k.com/Dolphin/)  
如果报错请下载[VC2015-2019 x64](https://learn.microsoft.com/en-US/cpp/windows/latest-supported-vc-redist?view=msvc-170) [备用下载](https://file.waterlemons2k.com/vc2015-2019.x64.exe)  
解压后打开Dolphin.exe,第一次打开会弹出一个窗口，点否  
![first](/Dolphin-emu/first.png)  
接下来会弹出更新可用窗口，这里选择不要自动更新  
![update](/Dolphin-emu/update.png)  
点击视图-表单列以自定义每列显示的内容  
![custom](/Dolphin-emu/custom.png)
# 设置
在设置-Wii可以更改感应条位置、红外灵敏度、扬声器音量  
![wiiset](/Dolphin-emu/wiiset.png)  
然后点击路径-添加 将存放有Wii游戏的目录添加进去  
![Add](/Dolphin-emu/Add.png)
# 图形
点图形-常规  
![graphics](/Dolphin-emu/graphics.png)  
后端:`Direct3D 12`、`Direct3D 11`、`Vulkan`、`OpenGL` 逐个测试后选择最好的  
长宽比:拉伸到窗口大小 将图像拉伸至窗口大小

**[下载 Mii](https://file.waterlemons2k.com/Mii.wad)**
# 存档
要导出 Wii 存档，请点击 `工具(T)` -> `导出所有 Wii 存档`，然后选择导出目录，导出后结构如下：
```
private
└── wii
    └── title
        └── ID
            └── data.bin
```
如果导出成功，会提示`已导出 x 个存档`

要导入 Wii 存档，请点击 `工具(T)` -> `导入 Wii 存档...`，然后选择以`.bin`结尾的 Wii 存档文件。可能会弹窗询问`是否现在覆盖？`，选择`Yes`(是)，如下图所示：
![Overwrite-save-file](/Dolphin-emu/Overwrite-save-file.png)

如果导出成功，会提示`成功导入存档文件。`
# 直通
[下载Zadig](https://zadig.akeo.ie/) [备用下载](https://file.waterlemons2k.com/zadig-2.4.exe)（推荐使用`BCM2045A`或`CSR8510`芯片的蓝牙适配器）  
以管理员身份运行`Zadig`，点`Options` -> `List All Devices`  
![Zadig1](/Dolphin-emu/Zadig1.png)  
选择**libusbK**或**WinUSB**,点`Replace Driver`  
![Zadig2](/Dolphin-emu/Zadig2.png)  
安装完成!  
![Zadig3](/Dolphin-emu/Zadig3.png)  
今后如果出现无法配对的情况时，请尝试`Reinstall Driver`做最后的努力  
![Zadig4](/Dolphin-emu/Zadig4.png)  
如果提示安装失败，到设备管理器查看是否有驱动，有可以继续，没有请重试  
![devmgmt](/Dolphin-emu/devmgmt.png)  
回到`Dolphin`,点控制器，选直通蓝牙适配器  
![passthrough](/Dolphin-emu/passthrough.png)  
打开游戏点`控制器` -> `同步`，屏幕会出现黄字  
![dolphinsync](/Dolphin-emu/dolphinsync.png)  
在出现黄字的同时，打开手柄电池盖，按红色按钮`SYNC` [图片来源](https://www.businessinsider.com/how-to-sync-wii-remote)  
![wiisync](/Dolphin-emu/wiisync.jpg)  
手柄1号灯长亮表示连接成功，可以开始游戏，如果没亮多试几次，还不行重启电脑  
![1p](/Dolphin-emu/1p.png)  
完成!