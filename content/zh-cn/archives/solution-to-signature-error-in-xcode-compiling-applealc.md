---
title: "Xcode 编译applealc出现签名错误的解决方法"
slug: "solution-to-signature-error-in-xcode-compiling-applealc"
date: 2021-11-01T02:08:00.000Z
categories:
- 分享
tags:
- Xcode
---

##报错如下

In subcomponent: /Users/admin/Library/Developer/Xcode/DerivedData/AppleALC-fqueikknxpxowubueomyyxuwlnmg/Build/Products/Debug/AppleALC.kext/Contents/PlugIns/PinConfigs.kext/Contents/Info.plist.md5
Command CodeSign failed with a nonzero exit code

##解决方法
在Other Code Signing Flags添加参数--deep
