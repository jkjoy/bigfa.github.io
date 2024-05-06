---
title: "macOS一键安装homebrew国内镜像"
slug: "macOS一键安装homebrew国内镜像"
date: 2022-07-29T07:33:00.000Z
categories:
- 测试
tags:
- macOS
---

 - [X]  国内镜像的一键安装脚本

官方给出的一键安装由于墙的原因可能无法安装成功。
所以找到了一个国内镜像的一键安装脚本

```bash
/bin/zsh -c "$(curl -fsSL https://gitee.com/cunkai/HomebrewCN/raw/master/Homebrew.sh)"
```
