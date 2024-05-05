---
title: 在docker compose build 时出现DNS lookup error错误
id: d1b65c5d-ed2f-4822-b512-5047f1789506
date: 2023-12-27 08:36:15
auther: admin
excerpt: 在docker compose build 时出现DNS lookup error错误 解决方法 在/etc/docker/daemon.json 配置文件中指定 dns 配置 "dns"["223.5.5.5"] 即可
permalink: /archives/1703637466801
categories:
 - test
tags: 
 - docker
---

在docker compose build 时出现DNS lookup error错误
## 解决方法
在/etc/docker/daemon.json 配置文件中指定 dns 配置
```
"dns":["223.5.5.5"]
```
即可