---
title: "解除typecho的最大字数限制"
slug: "unlimit-maximum-word-count-for-typecho"
date: 2023-05-09T06:36:00.000Z
categories:
- 分享
tags:
- typecho
---

把contens表里的text字段类型设置为longtext
执行SQL
```sql
alter table typecho_contents modify text LONGTEXT
```
