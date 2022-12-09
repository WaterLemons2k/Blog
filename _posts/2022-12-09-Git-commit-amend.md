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

引用：https://cloud.tencent.com/developer/article/1730774