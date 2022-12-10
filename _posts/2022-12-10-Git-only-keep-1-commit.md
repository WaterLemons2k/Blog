---
layout: post
title: Git 只保留1条 commit
---

如果您需要 Git 仓库**只保留1条 commit**，您可以：
1. 首先，使用命令 `git checkout` 的 `--orphan` 选项创建一个空白分支（本文为 `temporary`）：
   ```
   git checkout --orphan temporary
   ```
2. 添加当前目录下所有文件：
   ```
   git add .
   ```
3. 提交 commit 到 Git 仓库（本文的 commit 信息为 `Initial commit`）：
   ```
   git commit -m "Initial commit"
   ```
4. 删除**只保留1条 commit**的分支（本文为 `main`）：
   ```
   git branch -d main
   ```
5. 重命名当前分支为**只保留1条 commit**的分支（本文为 `main`）：
   ```
   git branch -m main
   ```
5. 最后，强制推送到 Git 仓库：
   ```
   git push -f
   ```
完成！

参考：https://xiusin.github.io/post/git-zhi-bao-liu-zui-hou-yi-ci-ti-jiao-dai-ma/