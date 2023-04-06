---
layout: post
title: Git 修改上次提交
---

当我们将更改提交到 Git 仓库时，可能会漏掉文件或者需要修改 commit 信息，这时就可以使用命令 `git commit` 的 `--amend` 选项：
```
git commit --amend
```
接下来会要求你编辑 `COMMIT_EDITMSG` 文件，看起来像这样：
```
Summary

Description

# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# Date:      Thu Jan 1 08:00:00 1970 +0800
#
# On branch main
#
# Initial commit
#
# Changes to be committed:
#	new file:   README.md
#

```
第1行为概括，第3行为描述，修改后保存并退出。  
输入下列命令以强制推送到 Git 仓库：
```
git push -f
```
完成！

相关文章：
- [Git 删除 commit](Git-Delete-Commit)
- [Git 忽略文件修改](Git-skip-worktree)
- [Git 只保留1条 commit](Git-only-keep-1-commit)
- [Git 空提交和没有消息的提交](Git-empty-commit-and-empty-message)
- [Git 为文件添加执行权限](Git-update-index-chmod=+x)
- [Git 撤销上一次 commit](Git-reset-soft-HEAD~1)
- [Git 同步上游仓库](Git-fetch-upstream)

参考：[Git 修改已提交 commit 的信息 - 腾讯云开发者社区-腾讯云](https://cloud.tencent.com/developer/article/1730774)