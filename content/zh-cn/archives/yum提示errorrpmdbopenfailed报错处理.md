---
title: yum提示Error: rpmdb open failed 报错处理
id: 439
date: 2023-10-17 08:43:39
auther: admin
excerpt: 
permalink: /archives/yum%E6%8F%90%E7%A4%BAerrorrpmdbopenfailed%E6%8A%A5%E9%94%99%E5%A4%84%E7%90%86
categories:
tags: 
 - vps
 - yum
---



宝塔面板安装docker失败时报错，可以使用以下方法重建rpm

# rpmdb所在目录

```bash
cd /var/lib/rpm
```

# 清除原rpmdb文件

```bash
rm -f __db.*
```

# 重建rpm数据库

```bash
rpm --rebuilddb
```

# 清除所有yum的缓存

```bash
yum clean all
```