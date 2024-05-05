---
title: Xcode 编译applealc出现签名错误的解决方法
id: 304
date: 2023-10-17 08:43:39
auther: admin
excerpt: 报错如下解决方法在添加参数
permalink: /archives/solution-to-signature-error-in-xcode-compiling-applealc
categories:
 - note
tags: 
 - 407
 - 514
 - code
 - 516
 - 517
 - xcode
---

##报错如下

In subcomponent: /Users/admin/Library/Developer/Xcode/DerivedData/AppleALC-fqueikknxpxowubueomyyxuwlnmg/Build/Products/Debug/AppleALC.kext/Contents/PlugIns/PinConfigs.kext/Contents/Info.plist.md5
Command CodeSign failed with a nonzero exit code

##解决方法
在Other Code Signing Flags添加参数--deep