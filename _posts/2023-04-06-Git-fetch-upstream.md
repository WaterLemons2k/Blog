---
layout: post
title: Git 同步上游仓库
---

当我们 fork 仓库后可能会需要与上游仓库同步，最简单的方法是点击 fork 仓库主页的 `Sync fork` -> `Update branch`，但也可以使用 `git`：

1. 请先使用 `git clone` 将 fork 仓库克隆到本地，然后运行 `git remote -v` 查看本地的远程仓库：
   ```sh
   $ git remote -v
   origin  https://github.com/YOU/FORK.git (fetch)
   origin  https://github.com/YOU/FORK.git (push)
   ```

2. 如果没有 `upstream`，添加上游仓库（本文为 `https://github.com/OWNER/ORIGINAL.git`）：
   ```sh
   git remote add upstream https://github.com/OWNER/ORIGINAL.git
   ```

3. 再次查看本地的远程仓库：
   ```sh
   $ git remote -v
   origin  https://github.com/YOU/FORK.git (fetch)
   origin  https://github.com/YOU/FORK.git (push)
   upstream        https://github.com/OWNER/ORIGINAL.git (fetch)
   upstream        https://github.com/OWNER/ORIGINAL.git (push)
   ```

4. 运行 `git fetch upstream` 获取上游仓库的提交：
   ```sh
   $ git fetch upstream
   remote: Enumerating objects: 5, done.
   remote: Counting objects: 100% (5/5), done.
   remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
   Unpacking objects: 100% (3/3), done.
   From https://github.com/OWNER/ORIGINAL
    * [new branch]      main       -> upstream/main
   ```

5. 切换到准备与上游仓库同步的分支（本文为 `main`）：
   ```sh
   $ git checkout main
   Switched to branch 'main'
   ```

6. 将上游仓库的 commit 合并到本地分支：
   ```sh
   $ git merge upstream/main
   Updating 141fa1c..dfe3645
   Fast-forward
    README.md | 2 ++
    1 file changed, 2 insertions(+)
   ```

7. 如果需要，将本地分支推送到 fork 仓库：
   ```
   $ git push origin main
   Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
   To https://github.com/YOU/FORK
      141fa1c..dfe3645  main -> main
   ```

完成！

相关文章：
- [Git 删除 commit](Git-Delete-Commit)
- [Git 忽略文件修改](Git-skip-worktree)
- [Git 修改上次提交](Git-commit-amend)
- [Git 只保留1条 commit](Git-only-keep-1-commit)
- [Git 空提交和没有消息的提交](Git-empty-commit-and-empty-message) 
- [Git 为文件添加执行权限](Git-update-index-chmod=+x)
- [Git 撤销上一次 commit](Git-reset-soft-HEAD~1)

参考：
1. [Syncing a fork - GitHub Docs](https://docs.github.com/pull-requests/collaborating-with-pull-requests/working-with-forks/syncing-a-fork?platform=windows)
2. [Git Upstreams and Forks: A Complete How-To | Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials/git-forks-and-upstreams)