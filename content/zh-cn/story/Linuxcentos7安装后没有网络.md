---
title: "centos7安装后没有网络"
slug: "centos7-network"
date: 2022-11-29T01:56:00.000Z
categories:
- 测试
tags:
- linux
---


以`root`账号登陆
用`ip addr`命令查看网络参数。
打开`eth0`网卡的配置文件

```bash
vi /etc/sysconfig/network-scripts/ifcfg-eth0
```

把`NOBOOT`参数`no`，修改为`yes`
重启网络或者重启服务器都可
