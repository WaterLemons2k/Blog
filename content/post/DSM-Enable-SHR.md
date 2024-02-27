---
title: 群晖DSM启用SHR
date: 2022-06-29
---

部分运行 DSM 的群晖 NAS 不支持 Synology Hybrid RAID (SHR) [详情](https://kb.synology.cn/DSM/tutorial/Which_models_have_limited_support_for_Synology_Hybrid_RAID_SHR)，但可以通过编辑 `synoinfo.conf` 启用:

1. 转到 `控制面板` -> `终端机和 SNMP`，勾选`启动 SSH 功能`，点击应用
   ![SSH](/Other/DSM-SSH.png)
2. 使用 SSH 连接到 DSM，输入`sudo -i`切换到 root 账户，输入管理员密码
3. 切换成功后输入下列命令：

```
sed -i 's/supportraidgroup/support_syno_hybrid_raid/g' /etc.defaults/synoinfo.conf
```

重启 DSM，完成后即可创建 SHR 阵列

引用：https://www.vediotalk.com/archives/4154
