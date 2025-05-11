---
title: Git 忽略文件修改
date: 2022-12-05
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

相关文章：

- [Git 删除 commit](/Git-Delete-Commit)
- [Git 修改上次提交](/Git-commit-amend)
- [Git 只保留 1 条 commit](/Git-only-keep-1-commit)
- [Git 空提交和没有消息的提交](/Git-empty-commit-and-empty-message)
- [Git 为文件添加执行权限](/Git-update-index-chmod=+x)
- [Git 撤销上一次 commit](/Git-reset-soft-HEAD~1)
- [Git 同步上游仓库](/Git-fetch-upstream)

参考：[忽略 Git 存储库中的文件 - Azure Repos | Microsoft Learn](https://learn.microsoft.com/zh-cn/azure/devops/repos/git/ignore-files#use-git-update-index-to-ignore-changes)
