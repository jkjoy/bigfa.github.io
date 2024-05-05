---
title: 双网口黑群晖使用虚拟机安装LEDE进行科学上网
id: 334
date: 2023-10-17 08:43:39
auther: admin
excerpt: LEDE固件下载http//dsm.jkjoy.cn5000/sharing/pksfFxboA安装步骤1.把下载到的固件上传到自己的群晖NAS2.打开virtual machine manager-映像-新增3. 网络-新增-创建两个一个WAN一个LAN5. 虚拟机-新增-导入-硬盘镜像-选择
permalink: /archives/shuang-wang-kou-hei-qun-hui-shi-yong-xu-ni-ji-an-zhuang-lede-jin-xing-ke-xue-shang-wang
categories:
 - share
tags: 
 - 群晖
 - lede
 - 虚拟机
---

## LEDE固件下载
http://dsm.jkjoy.cn:5000/sharing/pksfFxboA
## 安装步骤
1.把下载到的固件上传到自己的群晖NAS
2.打开virtual machine manager-映像-新增
![uTools_1657270751326](https://blog-1312096806.cos.ap-guangzhou.myqcloud.com/halo/uTools_1657270751326.png)
3. 网络-新增-创建两个一个WAN一个LAN
![uTools_1657270946417](https://blog-1312096806.cos.ap-guangzhou.myqcloud.com/halo/uTools_1657270946417.png)
5. 虚拟机-新增-导入-硬盘镜像-选择固件
这里要注意的是网络选择LAN WAN，LAN一定要在WAN上面
6.运行
![uTools_1657271293474](https://blog-1312096806.cos.ap-guangzhou.myqcloud.com/halo/uTools_1657271293474.png)
LEDE后台地址为192.168.1.1也可以在上层路由器查看IP直接访问例如我的192.168.123.74
7.需要注意的是网络服务顺序，软路由的网关一定要在主路由网关之下
![uTools_1657271498009](https://blog-1312096806.cos.ap-guangzhou.myqcloud.com/halo/uTools_1657271498009.png)
至此已经结束
安装请参照
https://blog.dasbid.com/archives/333