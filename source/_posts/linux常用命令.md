---
title: Linux常用命令
date: 2021-03-12 22:58:40
categories: 
- Linux
- Linux常用命令
---
yum命令---用来安装下载删除软件包
安装 yum install 软件包
删除 yum remove 软件包
查找 yum search 软件包
找出以 pam 为开头的软件包 yum list pam*
yum与apt功能一样
yum用于centos,apt用于ubuntu


压缩/解压
tar
打包成tar.gz格式压缩包
tar -zcvf renwolesshel.tar.gz renwolesshel
解压tar.gz格式压缩包
tar zxvf renwolesshel.tar.gz

压缩成zip格式
zip -q -r renwolesshel.zip renwolesshel/
解压zip格式的压缩包
unzip renwolesshel.zip

查看CPU/内存
top

查看磁盘使用情况
df -h
du -h