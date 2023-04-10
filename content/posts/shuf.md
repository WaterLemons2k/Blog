---
title: 使用 shuf 生成随机排列
date: 2022-12-29
---

假设这里有一个名为 `line.txt` 的文件，内容如下：
```sh
$ cat line.txt
line1
line2
line3
line4
line5
```
使用 `shuf` 命令生成随机排列：
```sh
$ shuf line.txt
line2
line5
line4
line3
line1
```
使用 `-n` 选项以只生成 n 行：
```sh
$ shuf -n 2 line.txt
line3
line1
```
使用 `-o` 选项以输出到文件：
```sh
$ shuf line.txt -o output.txt
$ cat output.txt
line3
line5
line1
line2
line4
```
使用 `-r` 选项以允许重复生成：
```sh
$ shuf -rn 3 line.txt
line1
line2
line1
```
使用 `-e` 选项以从参数生成：
```sh
$ shuf -e line1 line2 line3 line4 line5
line4
line1
line3
line2
line5
```
使用 `-i` 选项以从指定范围生成：
```sh
$ shuf -i 1-5
5
2
3
1
4
```

从其它命令生成：
```sh
seq 5 | shuf
2
1
3
5
4
```
相关文章：[Bash 生成随机整数 - $RANDOM](/Bash-$RANDOM)

参考：
1. https://linux.cn/article-9635-1.html
2. https://man7.org/linux/man-pages/man1/shuf.1.html
3. https://www.geeksforgeeks.org/shuf-command-in-linux-with-examples/
4. https://learnbyexample.github.io/cli_text_processing_coreutils/shuf.html