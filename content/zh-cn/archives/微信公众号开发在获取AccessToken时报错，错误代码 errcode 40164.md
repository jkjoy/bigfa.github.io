---
title: 微信公众号开发在获取AccessToken时报错，错误代码 errcode 40164
id: 516
date: 2023-10-17 08:43:40
auther: admin
excerpt: 
permalink: /archives/wei-xin-gong-zhong-hao-kai-fa-zai-huo-qu-accesstoken-shi-bao-cuo--cuo-wu-dai-ma-errcode40164
categories:
 - share
tags: 
 - 微信公众号
---

## 问题描述

在获取 AccessToken 时报错：
 ``` 
 errcode 40164
 ```
API 调用发生错误：
```
{"errcode":40164,"ErrorCodeValue":40164,"errmsg":"invalid ip 106.214.46.33, not in whitelist hint: [jPUF_08441512]","P2PData":null}
```

## 问题分析

ip 不合法，不在白名单中，因此将该IP添加至白名单中。

`微信公众平台`->`基本配置`->`IP白名单`。

确定修改之后，系统会提示一个二维码，要用手机微信扫一下确认提交本次IP白名单配置操作，确定即可。