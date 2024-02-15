---
title: 禁用 Windows 11 的 MPO
date: 2024-02-15
---

在使用 Windows 11 时，可能会出现光标变白消失、黑屏、闪烁等情况。可以尝试运行来自 [Nvidia](https://nvidia.custhelp.com/app/answers/detail/a_id/5157) 的注册表文件 "[mpo_disable.reg](https://nvidia.custhelp.com/ci/fattach/get/824301808/0/filename/mpo_disable.reg)" 来禁用 MPO (Multi-Plane Overlay) 以解决此问题。

以下是禁用 MPO 的注册表文件。

```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\Dwm]
"OverlayTestMode"=dword:00000005
```

重启电脑即可。

参考：

- [After updating to NVIDIA Game Ready Driver 461.09 or newer, some desktop apps may flicker or stutter when resizing the window on some PC configurations | NVIDIA](https://nvidia.custhelp.com/app/answers/detail/a_id/5157)
- [Microsoft, AMD, Nvidia, are all sleeping on Windows 11 MPO display issues - Neowin](https://www.neowin.net/news/microsoft-amd-nvidia-are-all-sleeping-on-windows-11-mpo-display-issues/)
- [Win11 光标变白消失解决方案 - 哔哩哔哩](https://www.bilibili.com/read/cv20029000/)
