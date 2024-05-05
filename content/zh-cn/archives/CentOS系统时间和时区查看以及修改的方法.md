---
title: CentOS系统时间和时区查看以及修改的方法
id: 432
date: 2023-10-17 08:43:39
auther: admin
excerpt: 一、时间修改 远程连接到centos 或者直接登录系统 #date 查看系统时间 #date -s 修改时间 看下面的例子 #date -s  03/04/2013（将系统日期设定为2013年03月04日） #date -s  11038（将系统时间设定为上午 1038） 二、时区修改 先查看时
permalink: /archives/centos%E7%B3%BB%E7%BB%9F%E6%97%B6%E9%97%B4%E5%92%8C%E6%97%B6%E5%8C%BA%E6%9F%A5%E7%9C%8B%E4%BB%A5%E5%8F%8A%E4%BF%AE%E6%94%B9%E7%9A%84%E6%96%B9%E6%B3%95
categories:
 - note
tags: 
 - vps
 - centos
---



一、时间修改 
远程连接到centos 或者直接登录系统 
```bash
date    
```
/** 查看系统时间 **/
```bash
date -s  
```
/** 修改时间 **/

看下面的例子 
```bash
 date -s  03/04/2013（将系统日期设定为2013年03月04日） 
 date -s  110:38（将系统时间设定为上午 10:38） 
```
二、时区修改 先查看时区 date -R   
修改时区： （将Asia/shanghai-上海时区写入当前时区） 
```bash
cp -f /usr/share/zoneinfo/Asia/Shanghai     /etc/localtime
``` 
提示是否覆盖,输入Y回车, 然后 
```bash
date
``` 
查看时区和时间（CST,中国时区）