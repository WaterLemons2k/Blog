---
layout: post
title: Git 忽略文件修改
---

有时不想将本地的文件修改提交到 Git 仓库，若要忽略文件修改，可以使用命令 `git update-index` 的 `--skip-worktree` 选项：
```
git update-index --skip-worktree file
```
此时**不会**提交对 `file` 的修改。

若要恢复，请使用`--no-skip-worktree` 选项：
```
git update-index --no-skip-worktree file
```
此时**会**提交对 `file` 的修改。

引用：https://learn.microsoft.com/zh-cn/azure/devops/repos/git/ignore-files#use-git-update-index-to-ignore-changes