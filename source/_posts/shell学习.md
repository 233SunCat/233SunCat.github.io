---
title: shell学习
date: 2021-03-12 22:58:40
categories: 
- Linux
---
Shell工具特性直接解释，不编译
单引号
双引号：可以使用变量
删除变量 unset $a
./e.sh f1 f2 f3    f1,f2,f3是参数
特殊变量：这些变量可以反映出特殊参数
read &a &b &c
expr命令：
expr 3 + 5
expr 3 \* 4可以使用*转义符

vim e.sh
chmod +x e.sh
./e.sh

test命令

if命令