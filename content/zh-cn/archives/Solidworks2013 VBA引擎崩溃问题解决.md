---
title: Solidworks2013 VBA引擎崩溃问题解决
id: 435
date: 2023-10-17 08:43:39
auther: admin
excerpt: 
permalink: /archives/solidworks2013vba%E5%BC%95%E6%93%8E%E5%B4%A9%E6%BA%83%E9%97%AE%E9%A2%98%E8%A7%A3%E5%86%B3
categories:
tags: 
 - solidworks2013
 - vba引擎
 - 675
 - 笔记
---



今天打开Solidworks2013时候加载VBA引擎时提示vbe6ext.olb不能被加载。 ![](https://mrwen.oss-cn-shanghai.aliyuncs.com/2018/07/w136h2319126_1444734785_583.jpg) ![](https://mrwen.oss-cn-shanghai.aliyuncs.com/2018/07/w188h2319126_1444734775_256.jpg) 解决方法就是把 C:\\Program Files（x86）\\Common Files\\Microsoft Shared\\VBA\\VBA7.1 目录下的vbe6ext.olb文件复制到 C:\\Program Files\\Common Files\\Microsoft Shared\\VBA\\VBA7.1 重启Solidworks2013即可。