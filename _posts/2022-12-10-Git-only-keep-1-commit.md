---
layout: post
title: Git 只保留1条 commit
---

如果需要 Git 仓库**只保留1条 commit**，您可以：
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
6. 最后，强制推送到 Git 仓库：
   ```
   git push -f
   ```
完成！

相关文章：
- [Git 删除 commit](Git-Delete-Commit)
- [Git 忽略文件修改](Git-skip-worktree)
- [Git 修改上次提交](Git-commit-amend)
- [Git 空提交和没有消息的提交](Git-empty-commit-and-empty-message)
- [Git 为文件添加执行权限](Git-update-index-chmod=+x)
- [Git 撤销上一次 commit](Git-reset-soft-HEAD~1)
- [Git 同步上游仓库](Git-fetch-upstream)

参考：[GIT只保留最后一次提交代码 | 修心修己](https://xiusin.github.io/post/git-zhi-bao-liu-zui-hou-yi-ci-ti-jiao-dai-ma/)