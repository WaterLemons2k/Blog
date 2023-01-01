---
layout: post
title: Git 空提交和没有消息的提交
---

如果要将**空提交**推送到 Git 仓库，可以使用命令 `git commit` 的 `--allow-empty` 选项：
```
git commit --allow-empty -m "Empty commit"
```
如果要将**没有消息的提交**推送到 Git 仓库，可以使用命令 `git commit` 的 `--allow-empty-message` 选项：
```
git add .
git commit --allow-empty-message -m ""
```
最后，推送到 Git 仓库：
```
git push
```
相关文章：
- [Git 删除 commit](Git-Delete-Commit)
- [Git 忽略文件修改](Git-skip-worktree)
- [Git 修改上次提交](Git-commit-amend)
- [Git 只保留1条 commit](Git-only-keep-1-commit)
- [Git 为文件添加执行权限](Git-update-index-chmod=+x)

参考：
1. [如何在 Git 中推送一个空的提交](https://www.freecodecamp.org/chinese/news/how-to-push-an-empty-commit-with-git/)
2. [Git commit with no commit message - Stack Overflow](https://stackoverflow.com/questions/6218199)