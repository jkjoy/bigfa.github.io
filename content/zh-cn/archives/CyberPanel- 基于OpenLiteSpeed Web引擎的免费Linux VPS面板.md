---
title: CyberPanel- 基于OpenLiteSpeed Web引擎的免费Linux VPS面板
id: 433
date: 2023-10-17 08:43:39
auther: admin
excerpt: 
permalink: /archives/cyberpanel-%E5%9F%BA%E4%BA%8Eopenlitespeedweb%E5%BC%95%E6%93%8E%E7%9A%84%E5%85%8D%E8%B4%B9linuxvps%E9%9D%A2%E6%9D%BF
categories:
tags: 
 - vps
 - cyberpanel
 - linux
---



最近去CyberPanel官方看到，版本已经到V1.6版本，且基本的功能应该算成熟。不过目前的用户也并不是很多，这个应该与官方的实际推广宣传力度有关系，当然还有很多国内用户的使用习惯，因为毕竟作为面板而言我们选择一个习惯的就可以，也没有必要使用太多的。在这篇文章中，将体验CyberPanel免费面板的安装与基本功能应用。

### 1、配置要求

根据官方的要求，需要服务器系统使用的Centos 7.x、Python 2.7、内存512MB、硬盘10GB以上。

### 2、一键安装包

```
yum install curl curl-devel wget -y
sh <(curl https://cyberpanel.net/install.sh || wget -O - https://cyberpanel.net/install.sh)
```

可以直接一键安装最新版本。 安装完毕，看到登入地址和用户名和密码。

### 3、CyberPanel登入

登入CyberPanel面板，我们可以选择Chinese简体中文。因为面板自带语言包的，我们登入进入后看到简体中文。看到CyberPanel面板后台，体验还是比较好的。毕竟OpenLiteSpeed团队，华人还是比较多的，所以还是有针对性的希望让中文用户使用。