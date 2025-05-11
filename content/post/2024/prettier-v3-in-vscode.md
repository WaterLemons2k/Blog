---
title: 在 prettier-vscode 插件中使用 Prettier 3
date: 2024-06-05
---

截至本文发布，prettier-vscode v10.4.0 仍不支持导入属性（Import Attributes）。这是因为其仍在使用 [Prettier 2.8.8](https://github.com/prettier/prettier-vscode/blob/v10.4.0/package.json#L130)，而导入属性要到 [Prettier 3.1.1](https://github.com/prettier/prettier/releases/tag/3.1.1) 才会支持。

所以，本篇文章将会介绍如何在 prettier-vscode 中使用更新版本的 Prettier。

## 使用更新版本的 Prettier

### 安装 Prettier

```sh
pnpm update prettier --latest
```
