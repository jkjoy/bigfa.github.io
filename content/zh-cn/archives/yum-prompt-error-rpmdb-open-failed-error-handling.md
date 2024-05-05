---
title: yum提示Error: rpmdb open failed 报错处理
id: 322
date: 2023-10-17 08:43:39
auther: admin
excerpt: 所在目录清除原文件重建数据库清除所有的缓存
permalink: /archives/yum-prompt-error-rpmdb-open-failed-error-handling
categories:
 - share
tags: 
 - 文件
 - 554
 - yum
 - 556
 - 清除
 - 558
---

 ```
cd /var/lib/rpm
```
  # rpmdb所在目录


 ```
 rm -f __db.* 
```
     
   # 清除原rpmdb文件

 ```
rpm --rebuilddb
```    
     
   # 重建rpm数据库

     yum clean all    
     
   # 清除所有yum的缓存