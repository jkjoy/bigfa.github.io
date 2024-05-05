---
title: centos安装nonebot2使用qq机器人
id: 363
date: 2023-10-17 08:43:39
auther: admin
excerpt: 安装Python根据文档，最低安装的版本为3.7.3那我们就安装一下3.7.6下载wget https//www.python.org/ftp/python/3.7.6/Python-3.7.6.tgz创建目录mkdir -p /usr/local/python3解压tar -zxvf Pytho
permalink: /archives/centos-an-zhuang-nonebot2-shi-yong-qq-ji-qi-ren
categories:
 - note
 - share
tags: 
 - centos
 - qq机器人
 - python
---

## 安装Python
根据文档，最低安装的版本为3.7.3

那我们就安装一下3.7.6
- 下载
```
wget https://www.python.org/ftp/python/3.7.6/Python-3.7.6.tgz
```
- 创建目录
```
mkdir -p /usr/local/python3
```
- 解压
```
tar -zxvf Python-3.7.6.tgz
```
- 安装依赖
```
yum -y install gcc
yum -y install zlib*
yum install readline-devel
```
- 配置
```
cd Python-3.7.6
./configure --prefix=/usr/local/python3
```
- 编译
```
make && make install
```
- 建立软链接
```
ln -s /usr/local/python3/bin/python3.7 /usr/bin/python3
ln -s /usr/local/python3/bin/pip3.7 /usr/bin/pip3
```
## 安装nonebot2
一键安装
```
pip3 install nb-cli -i http://pypi.douban.com/simple/ --trusted-host pypi.douban.com 
```
可能遇到pip版本不匹配，需要升级
```
/usr/local/python3/bin/python3.7 -m pip install --upgrade pip -i http://pypi.douban.com/simple/ --trusted-host pypi.douban.com
```