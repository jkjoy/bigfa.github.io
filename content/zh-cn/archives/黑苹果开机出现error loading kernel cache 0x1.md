---
title: 黑苹果开机出现error loading kernel cache 0x1
id: 205
date: 2023-10-17 08:43:38
auther: admin
excerpt: 出现这个错误的原因是系统缓存出现错误在上看到国外黑苹果论坛给出了解决办法进入苹果安装盘打开终端工具命令行安装分区安装分区注意安装分区名称如果有空格记得在后面加“”会出现提示删除他们安装分区
permalink: /archives/black-apple-boot-error-cache-kenel
categories:
 - note
tags: 
 - 错误
 - 系统
---

出现这个错误的原因是系统缓存出现错误
在google上看到国外黑苹果论坛给出了解决办法

进入苹果安装盘
打开终端工具   命令行
df -h

touch /Volumes/macOS安装分区/System/Library/Extensions && kextcache -u /Volumes/macOS安装分区
注意macOS安装分区名称如果有空格记得在后面加“\”
会出现提示
Child process [directory] has exited due to signal 10

Error 107 rebuilding /System/Library/PrelinkedKernels/prelinkedkernel
删除他们
rm -f /Volumes/macOS安装分区/System/Library/PrelinkedKernels/prelinkedkernel