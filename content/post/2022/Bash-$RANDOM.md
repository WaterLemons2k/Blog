---
title: Bash 生成随机整数 - $RANDOM
date: 2022-12-25
---

`$RANDOM` 是 Bash 的内建函数，它会生成 0 - 32767 之间的伪随机整数，您可以输入下列命令以显示：

```bash
echo $RANDOM
```

生成 1 - 10 之间的随机数：

```bash
echo $((RANDOM %10 + 1))
```

相关文章：[使用 shuf 生成随机排列](/shuf)

参考：

1. https://tldp.org/LDP/abs/html/randomvar.html
2. https://stackoverflow.com/questions/1194882/how-to-generate-random-number-in-bash
