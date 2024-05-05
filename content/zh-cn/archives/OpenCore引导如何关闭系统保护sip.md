---
title: OpenCore引导如何关闭系统保护sip
id: 223
date: 2023-10-17 08:43:38
auther: admin
excerpt: 关闭系统保护方法；——填入值：如果安装出现进入安装界面空白则需要开启。
permalink: /archives/opencore-boot-how-to-turn-off-system-protection-sip
categories:
 - share
tags: 
 - 系统
 - opencore
 - 425
 - 426
 - 427
 - 428
---

OpenCore 关闭系统保护方法；

NVRAM — 7C436110-AB2A-4BBB-A880-FE41995C9F82 — csr-active-config 填入DATA值：

    E7030000

如果安装出现进入安装界面空白 则需要开启SIP。
