---
title: linux下一键搭建SS
id: 99
date: 2023-10-17 08:43:38
auther: admin
excerpt: 事实上都可以使用此命令行
permalink: /archives/ubuntu-next-key-to-build-ss
categories:
 - note
tags: 
 - wget
 - 201
---

事实上Ubuntu centos都可以使用此命令行

```
wget --no-check-certificate https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks.sh
chmod +x shadowsocks.sh 
./shadowsocks.sh 2&gt;&amp;1 | tee shadowsocks.log
```
