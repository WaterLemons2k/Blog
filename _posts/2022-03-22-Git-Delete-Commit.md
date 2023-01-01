---
layout: post
title: Git 删除 commit
---
1. 首先，输入下列命令查看历史提交的 commit（按Q退出）：
   ```
   git log
   ```
2. 找到要删除的 commit，记住 commit 信息下一行的 `commit`，如图中红框所示：  
   ![log](/assets/Git-Delete-Commit/log.png)
3. 然后执行：
   ```
   git rebase -i commit 
   ```
4. 根据 commit 信息将被删除 `commit` 前面的 `pick` 替换为 `drop` ，**再三考虑后保存并退出**：  
   ![pick](/assets/Git-Delete-Commit/pick.png)
5. 再次输入下列命令检查 `commit` 是否被删除：
   ```
   git log 
   ```
6. 最后，输入下列命令推送至 Git 仓库：
   ```
   git push origin HEAD --force
   ```
完成！

相关文章：[Git 忽略文件修改](Git-skip-worktree) [Git 修改上次提交](Git-commit-amend) [Git 只保留1条 commit](Git-only-keep-1-commit) [Git 空提交和没有消息的提交](Git-empty-commit-and-empty-message) [Git 为文件添加执行权限](Git-update-index--chmod=+x)

参考：[强迫症如何干净删除 commit 记录 - 腾讯云开发者社区-腾讯云](https://cloud.tencent.com/developer/article/1511875)