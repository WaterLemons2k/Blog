---
title: Debian 禁止软件更新
date: 2023-01-17
---

如果需要禁止更新 Debian 的特定软件，可以使用以下命令：

```
apt-mark hold
```

例如，如果需要禁止更新 `linux-image-amd64`，可以运行：

```
apt-mark hold linux-image-amd64
```

此时 **不会** 更新 `linux-image-amd64`。

要恢复，请运行：

```
apt-mark unhold linux-image-amd64
```

此时 **会** 更新 `linux-image-amd64`。
