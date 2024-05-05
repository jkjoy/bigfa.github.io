---
title: pip安装使用出现ImportError: No module named setuptools
id: 364
date: 2023-10-17 08:43:39
auther: admin
excerpt: 
permalink: /archives/pip-an-zhuang-shi-yong-chu-xian-importerrornomodulenamedsetuptools
categories:
 - note
tags: 
 - python
---

### 下载
```
wget --no-check-certificate https://pypi.python.org/packages/source/s/setuptools/setuptools-12.0.3.tar.gz#md5=f07e4b0f4c1c9368fcd980d888b29a65
```
### 解压
```
tar xvf setuptools-12.0.3.tar.gz
```
### 安装
```
cd setuptools-12.0.3
python setup.py install
```