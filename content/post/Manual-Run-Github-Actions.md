---
title: 手动运行Github Actions
date: 2022-09-13
---

Github Actions 默认不启用手动运行，但可以通过更改 YAML 文件来实现，步骤如下:

1.  找到要运行 Github Actions 项目的主分支(master 或 main)，找到`.github/workflows`文件夹
2.  打开 Workflow 的配置文件(扩展名为.yml)
3.  在文件的`on:`处另起一行，添加`workflow_dispatch:`，看起来像这样:

```
on:
  workflow_dispatch:
```

4.  然后点击右上角绿色的`Start Commit` -> `Commit changes`提交更改
5.  点击`Actions`，选择要运行的`Workflow`，当看到`This workflow has a workflow_dispatch event trigger.`时，点击两次`Run workflow`  
    ![Run](/Other/GitHub-manual-Run-workflow.png)
6.  稍等一会，当出现`Workflow`时，完成!
