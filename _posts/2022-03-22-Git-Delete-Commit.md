---
layout: post
title: Git删除Commit
---
1.  输入以下命令来查看历史提交的commit（按Q退出）
```
git log
```
2.  找到被删除commit的注释，记住下一行的`commit号`(如图中红框)  
![log](/assets/Git-Delete-Commit/log.png)
3.  然后执行：
```
git rebase -i commit 
```
将commit替换为`commit号`

![pick](/assets/Git-Delete-Commit/pick.png)  
4.将被删除commit前面的`pick`替换为`drop`，**再三考虑后保存**  
5.输入以下命令检查是否被删除
```
git log 
```
6.最后输入以下命令推送至仓库即可
```
git push origin HEAD --force
```
完成!  
引用:https://cloud.tencent.com/developer/article/1511875