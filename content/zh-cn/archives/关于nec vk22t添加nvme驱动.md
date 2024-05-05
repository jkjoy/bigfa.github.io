---
title: 关于nec vk22t添加nvme驱动
id: 264
date: 2023-10-17 08:43:38
auther: admin
excerpt: 昨天尝试把芯片焊下来然后用把驱动添加进用编程器写入之后发现无法开机。用编程器备份的是，用工具备份下来的只有。后来没有继续尝试的原因是我把主板上的焊盘搞坏了。算了。尝试计划至此被动完结。笔记本目前已经被我肢解。对于我能给的建议就是直接用盘来引导吧这样至少安全点少折腾还能省钱在外网找到了一个版的模块或许有用
permalink: /archives/about-nec-vk22t-adding-nvme-driver
categories:
 - share
tags: 
 - 原因
 - 驱动
 - 主板
 - nvme
 - 笔记本
 - bios
 - 尝试
 - 481
 - 编程器
 - 焊盘
---

昨天尝试把bios芯片焊下来然后用uefitool把nvme驱动添加进bios
用编程器写入之后发现无法开机。
用编程器备份的bios是8m，用amibios工具备份下来的只有6m。
后来没有继续尝试的原因是我把主板上的焊盘搞坏了。算了。
bios尝试计划至此被动完结。
笔记本目前已经被我肢解。
对于nvme我能给的建议就是直接用u盘来引导吧 这样至少安全点
少折腾还能省钱-_-

在外网找到了一个small版的模块或许有用
https://blog.asbid.cn/nvme-module-small.html