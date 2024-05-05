---
title: opencore引导界面USB键盘鼠标失效的解决办法
id: 328
date: 2023-10-17 08:43:39
auther: admin
excerpt: 无法在选择器中选择任何内容这是由于某些原因不兼容的键盘驱动程序：中禁用并启用，然后从您的子项删除驱动如果上述方法无效，请反向操作：在中禁用，然后把驱动添加到您的下面
permalink: /archives/solution-of-usb-keyboard-and-mouse-failure-in-opencore-boot-interface
categories:
 - share
tags: 
 - 原因
 - 驱动
 - opencore
---

无法在选择器中选择任何内容这是由于某些原因不兼容的键盘驱动程序：
**config.plist**中禁用**PollAppleHotKeys**并启用**KeySupport**，然后从您的config.plist-**UEFI**-**Drivers** 子项删除**OpenUsbKbDxe**驱动
如果上述方法无效，请反向操作：在**config.plist**中禁用**KeySupport**，然后把**OpenUsbKbDxe**
驱动添加到您的**config.plist**-**UEFI**-**Drivers**  下面