---
title: "Git在windows下区分大小写"
date: 2023-03-21T11:03:00.000Z
categories:
- 分享
tags:
- git
---

在`.deploy_git`目录下运行
```bash
git config core.ignorecase false
```
可解决github pages 下CNAME被改为小写导致绑定域名失效的情况
