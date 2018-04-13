---
title: 使用GCC
date: 2018-04-12 21:36:59
categories:
 - Skills
tags:
 - Linux
---

如何在Ubuntu下安装/卸载/使用gcc。
Linux下最常用的C语言编译器是GCC（GNU Compiler Collection）,它是GNU项目中符合ANSI C标准的编译系统,能够编译用C、C++和Object C等语言编写的程序。

### 安装gcc
```shell
sudo apt-get install build-essential
```
该命令会安装一些必要的包，如g++，gcc等

### 查看gcc版本
```shell
gcc --version
```
在Linux系统中，查看版本信息，一般都是这个参数version

### 卸载gcc
```shell
sudo apt-get remove gcc
```

### 使用gcc
 - 预处理：
```shell
gcc -Ehello.c -o hello.i //生成预处理后的源文件
```
 - 汇编：
```shell
gcc -S hello.i //生成hello.s
```
 - 目标代码生成：
```shell
gcc -c hello.s //生成hello.o
```
 - 连接：
```shell
gcc hello.o -o hello //生成可以行文件hello
```

简单直接的运行方法：
```shell
# gcc hello.c -o hello //直接生成可执行文件hello
# ./hello              //运行可执行文件
```

文件类型说明：
.a    静态库文件
.o  目标文件
.i  预处理后的源文件
.s  汇编文件
.so 共享库文件


