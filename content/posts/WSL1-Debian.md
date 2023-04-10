---
title: WSL 1 安装 Debian
date: 2023-01-13
---

要使用 WSL 1 安装 Debian，请先确保已启用 `适用于 Linux 的 Windows 子系统`。  
如果还没有启用，**以管理员身份运行 PowerShell** 并执行下列命令：
```PowerShell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```
**重启电脑**后继续。

如果您已成功启用 WSL 1，执行下列命令以安装 Debian：
```PowerShell
wsl --install -d Debian
```
执行下列命令以查看其它可用系统：
```PowerShell
wsl --list --online
```
参考：[旧版 WSL 的手动安装步骤 | Microsoft Learn](https://learn.microsoft.com/zh-cn/windows/wsl/install-manual)