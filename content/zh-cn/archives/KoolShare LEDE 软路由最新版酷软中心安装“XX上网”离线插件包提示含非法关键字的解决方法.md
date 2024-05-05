---
title: KoolShare LEDE 软路由最新版酷软中心安装“XX上网”离线插件包提示含非法关键字的解决方法
id: 333
date: 2023-10-17 08:43:39
auther: admin
excerpt: 
permalink: /archives/koolsharelede-ruan-lu-you-zui-xin-ban-ku-ruan-zhong-xin-an-zhuang-xx-shang-wang--li-xian-cha-jian-bao-ti-shi-han-fei-fa-guan-jian-zi-de-jie-jue-fang-fa
categories:
 - share
tags: 
 - 566
 - lede
 - 568
---

用SSH登录软路由
```
ssh root@192.168.1.1
```
然后输入

```bash
sed -i 's/\tdetect_package/\t# detect_package/g' /koolshare/scripts/ks_tar_install.sh
```
OK。
([下载地址](https://blog-1312096806.cos.ap-guangzhou.myqcloud.com/halo/koolss_2.2.2.tar.gz))