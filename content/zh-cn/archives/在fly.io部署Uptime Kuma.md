---
title: 在fly.io部署Uptime Kuma
id: dd8b0937-082a-4cc7-9d13-b4662912c2e3
date: 2023-12-29 11:01:24
auther: admin
excerpt: # Uptime Kuma Uptime Kuma是一个监控面板 准备 fly.io的账号 fly的命令行工具 具体步骤 创建一个目录 在该目录下执行 flyctl launch 会提示如下 Scanning source codeCould not find a Dockerfile, nor
permalink: /archives/1703818863843
categories:
 - share
tags: 
 - bu-shu
 - uptime-kuma
---

​#  Uptime Kuma
Uptime Kuma是一个监控面板
## 准备
fly.io的账号
fly的命令行工具
## 具体步骤
创建一个目录
在该目录下执行
```bash
flyctl launch
```
会提示如下
```bash
Scanning source code
Could not find a Dockerfile, nor detect a runtime or framework from source code. Continuing with a blank app.
Creating app in C:\Users\Administrator\Desktop\uptime
We're about to launch your app on Fly.io. Here's what you're getting:

Organization: albert sun             (fly launch defaults to the personal org)
Name:         uptime                 (derived from your directory name)
Region:       Hong Kong, Hong Kong   (this is the fastest region for you)
App Machines: shared-cpu-1x, 1GB RAM (most apps need about 1GB of RAM)
Postgres:     <none>                 (not requested)
Redis:        <none>                 (not requested)

? Do you want to tweak these settings before proceeding?
```
此时按`Y`,根据弹出的网页填写,选择256MB 服务器所在地为HKG 
根目录下会生成`fly.toml`文件
继续执行
```bash
flyctl volumes create uptime_data --region hkg --size 1
```
创建一个服务所在地 为香港的1g的持久卷
修改`fly.toml`文件内容
以下仅供参考
```yaml
# fly.toml app configuration file generated for uptime00 on 2023-12-29T10:46:36+08:00
#
# See https://fly.io/docs/reference/configuration/ for information about how to use this file.
#

app = "uptime00"
primary_region = "hkg"

[build]
  image = "louislam/uptime-kuma:latest"

[[mounts]]
  source = "uptime_data"
  destination = "/app/data"

[http_service]
  internal_port = 3001
  force_https = true
  auto_stop_machines = false
  auto_start_machines = true
  min_machines_running = 0
  processes = ["app"]

[[vm]]
  cpu_kind = "shared"
  cpus = 1
  memory_mb = 256
```
修改完成后
执行
```bash
fly deploy
```
即可


## 演示地址
https://uptime00.fly.dev/
绑定域名演示
https://www.0tz.top

原文地址