---
title: "宝塔面板数据库有时候自动停止用计划任务来解决的办法"
slug: "sometimes-the-pagoda-panel-database-automatically-stops-using-the-planned-task-to-solve-the-problem"
date: 2023-05-23T06:59:00.000Z
categories:
- 分享
tags:
- 宝塔
---

创建计划任务,每分钟执行一次
脚本如下

```
pgrep -x mysqld &> /dev/null
if [ $? -ne 0 ];then
/etc/init.d/mysqld start 
fi
```
检测数据库状态并自动启动
