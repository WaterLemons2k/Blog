---
layout: post
title: 群晖DSM启用SHR
---
部分运行DSM的群晖NAS不完全支持Synology Hybrid RAID (SHR) [详情](https://kb.synology.cn/DSM/tutorial/Which_models_have_limited_support_for_Synology_Hybrid_RAID_SHR)，但可以通过编辑 synoinfo.conf启用:

1. 启用控制面板-终端机和 SNMP-启动 SSH 功能，点应用
![SSH](/assets/Other/DSM-SSH.png)
2. 使用SSH软件连接到群晖，或输入`ssh admin@IP`连接(将admin替换为群晖管理员账户，IP替换为群晖IP)，输入管理员密码
3. 输入`sudo -i`切换到root账户，再次输入管理员密码
4. 切换到root账户成后，输入下列命令以编辑synoinfo.conf:
```
vi /etc.defaults/synoinfo.conf
```
5. 按一次Esc,输入
```
/supportraidgroup
```
6. 找到`supportraidgroup="yes"`后按回车结束查找，按键盘上的Insert或I键，在开头加#号以注释此行，然后另起一行，输入:
```
support_syno_hybrid_raid=”yes”
```
7. 输入完成后按Esc，然后输入:wq保存文件，重启DSM，完成后即可创建SHR阵列

引用:https://www.vediotalk.com/archives/4154