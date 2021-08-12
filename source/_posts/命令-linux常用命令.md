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
df -h//查看磁盘分区的磁盘空间
du -sh//查看目录或者文件的空间

> linux的权限设置 chmod [-R] xyz 文件或目录
> 文件属性rwxrwxrwx,分别代表拥有者+组内其他用户+其他用户
> r:4,w:2,x1   (r,可读，w可写，x可执行)
>
> ```c
> [root@www ~]# ls -al .bashrc
> -rw-r--r--  1 root root 395 Jul  4 11:45 .bashrc
> [root@www ~]# chmod 777 .bashrc//7-rwx,6-rw,3-wx依次类推
> [root@www ~]# ls -al .bashrc
> -rwxrwxrwx  1 root root 395 Jul  4 11:45 .bashrc
> ```

> 精通shell脚本

1.查看文件的后五行(使用tail命令)：tail nowcoder.txt -n5   或者 tail -5 nowcoder.txt 
2.查看文件的前五行(使用head命令)：head nowcoder.txt -n5   或者 head -5 nowcoder.txt 
3.0到500中7的倍数：
for num in {0..500..7}; do 
  echo "${num}"
done

4.输出文本的第五行内容(head组合tail)：head -5 nowcoder.txt | tail -1

总结一下：1.查看文件前100行： head -100 nowcoder.txt   2.查看文件后100行：tail -100 nowcoder.txt 
3.查看文件中间100行到200行的内容：sed -n ‘100,200p’ nowcoder.txt 