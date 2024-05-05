---
title: CentOS一键安装ShadowsocksR服务(附单/多端口管理)
id: 177
date: 2023-10-17 08:43:38
auther: admin
excerpt: 使用命令下载文件，代表不重新下载文件除非比本地文件更新，代表不检查证书。下载完成后可以看到以下界面，按提示操作输入端口密码加密方式协议混淆等参数即可完成安装。安装完成后，如需要进入服务界面输入以下命令。安装完成后，自动设置为系统服务，所以支持使用服务来启动停止等操作，同时支持开机启动。
permalink: /archives/centos-oneclick-installation-of-shadowsocksr-service-billmultiport-management
categories:
 - share
tags: 
 - 276
 - 21
 - wget
 - 文件
 - 280
 - 安装
 - 282
 - service
 - 列表
---

命令如下
```
wget -N --no-check-certificate https://raw.githubusercontent.com/ToyoDAdoubi/doubi/master/ssr.sh && chmod +x ssr.sh && bash ssr.sh
```

<p>使用wget命令下载文件，-N代表不重新下载文件除非比本地文件更新，--no-check-certificate代表不检查证书。</p>
<p>下载完成后可以看到以下界面，按提示操作输入端口/密码/加密方式/ 协议/混淆等参数即可完成安装。
<img src="https://xy07-1251893119.costj.myqcloud.com/2019/04/03/4001117836.png" alt="20190211153929924.png" />
安装完成后，如需要进入服务界面输入以下命令。</p>
<pre><code>bash ssr.sh</code></pre>
<p>安装完成后，自动设置为系统服务，所以支持使用服务来启动/停止等操作，同时支持开机启动。</p>
<blockquote>
<p>service ssr start    //启动 
service ssr stop    //停止<br />
service ssr restart //重启 
service ssr status</p>
</blockquote>
<p>ShadowsocksR 默认支持UDP转发，服务端无需任何设置。</p>
<p>本脚本已经集成了 安装/卸载 锐速(ServerSpeeder)，但是是否支持请查看 Linux支持内核列表 。</p>