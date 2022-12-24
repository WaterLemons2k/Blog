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
参考：https://www.freecodecamp.org/chinese/news/how-to-push-an-empty-commit-with-git/  
https://stackoverflow.com/questions/6218199/git-commit-with-no-commit-message