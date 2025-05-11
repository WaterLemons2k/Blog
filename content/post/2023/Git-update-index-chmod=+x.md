---
title: Git 为文件添加执行权限
date: 2023-01-01
---

假设这里有一个名为 `file.sh` 的文件，内容如下：

```sh
#!/bin/sh
echo Hello, World!
```

要让此文件在上传到 Git 仓库后保留执行权限，您可以：

1. 首先，将 `file.sh` 添加到本地 Git 仓库：
   ```
   git add file.sh
   ```
2. 然后，使用命令 `git ls-files` 的 `-s` 选项查看文件权限：

   ```
   $ git ls-files -s
   100644 131b6b8bb46c8286541c6503f94b21a1fd25b200 0	file.sh
   ```

   现在的权限是 `644`，**没有执行权限**

3. 使用命令 `git update-index` 的 `--chmod=+x` 选项为文件添加执行权限：
   ```
   git update-index --chmod=+x file.sh
   ```
4. 再次查看文件权限：
   ```
   $ git ls-files -s
   100755 131b6b8bb46c8286541c6503f94b21a1fd25b200 0	file.sh
   ```
   现在的权限是 `755`，**拥有执行权限**
5. 将 commit 提交到本地 Git 仓库：
   ```
   git commit -m "Add file.sh"
   ```
6. 最后，推送到远程 Git 仓库：
   ```
   git push
   ```
   完成！

相关文章：

- [Git 删除 commit](/Git-Delete-Commit)
- [Git 忽略文件修改](/Git-skip-worktree)
- [Git 修改上次提交](/Git-commit-amend)
- [Git 只保留 1 条 commit](/Git-only-keep-1-commit)
- [Git 空提交和没有消息的提交](/Git-empty-commit-and-empty-message)
- [Git 撤销上一次 commit](/Git-reset-soft-HEAD~1)
- [Git 同步上游仓库](/Git-fetch-upstream)

参考：

1. [Git - git-update-index Documentation](https://git-scm.com/docs/git-update-index#Documentation/git-update-index.txt---chmod-x)
2. [How to add chmod permissions to file in Git? - Stack Overflow](https://stackoverflow.com/questions/40978921)
