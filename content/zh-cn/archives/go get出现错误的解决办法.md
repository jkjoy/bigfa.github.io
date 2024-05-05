---
title: go get出现错误的解决办法
id: 219
date: 2023-10-17 08:43:38
auther: admin
excerpt: 错误提示解决办法
permalink: /archives/solutions-to-go-get-errors
categories:
 - share
tags: 
 - 链接
 - 错误
 - 345
 - 407
 - 408
 - 409
 - 410
 - 411
 - 412
---

错误提示
unrecognized import path "golang.org/x/sys/windows": https fetch: Get "https://golang.org/x/sys/windows?go-get=1": dial tcp 216.239.37.1:443: connectex: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.
解决办法

mkdir -p $GOPATH/src/golang.org/x
cd $GOPATH/src/golang.org/x
git clone https://github.com/golang/sync.git
git clone https://github.com/golang/crypto.git
git clone https://github.com/golang/sys.git
————————————————

原文链接：https://blog.csdn.net/cyLee_/java/article/details/93159032