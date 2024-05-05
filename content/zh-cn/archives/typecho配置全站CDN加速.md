---
title: "Typecho配置全站CDN加速"
slug: "typecho配置全站CDN加速"
date: 2023-04-06T08:15:00.000Z
categories:
- 分享
tags:
- CDN
---

 >由于全站使用CDN加速，进入后台时出现页面异常，登录不上

 这里以又拍云为例

 - 在源站设置

 ![1.png](https://s2.loli.net/2023/04/06/bfHAkDU3sPOFTc7.png)
 如果你的源站使用SSL，CDN也使用SSL，就选择协议跟随

 - 在缓存设置

 ![2.png](https://s2.loli.net/2023/04/06/Otbe4Faiz5PYH6S.png)

 ![3.png](https://s2.loli.net/2023/04/06/cNbv3axJ6pG7PkK.png)
如果使用伪静态就不用排除	
`/index.php/action/*`

 - 参数跟随

 ![4.png](https://s2.loli.net/2023/04/06/vuLzsY2hH78jZgP.png)
