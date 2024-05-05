---
title: 快速部署misskey实例
id: 1b5bd7b8-84d2-4af7-9aa2-5e848a87f181
date: 2023-12-27 08:40:07
auther: admin
excerpt: 使用官方推荐一键脚本 使用纯净的Ubuntu系统安装,推荐配置双核心四线程. 更新软件 sudo apt update; sudo apt full-upgrade -y; sudo reboot 一键脚本 wget https//raw.githubusercontent.com/joinmi
permalink: /archives/1703637814865
categories:
 - note
tags: 
 - docker
---


## 使用官方推荐一键脚本
使用纯净的Ubuntu系统安装,推荐配置双核心四线程.
### 更新软件
```
sudo apt update; sudo apt full-upgrade -y; sudo reboot
```
### 一键脚本
```
wget https://raw.githubusercontent.com/joinmisskey/bash-install/main/ubuntu.sh -O ubuntu.sh; sudo bash ubuntu.sh
```
按照提示输入内容
### 更新misskey脚本
更新 Misskey 的脚本不会升级运行环境。 对于脚本的更新内容，另请参阅 “更新日志”
```
wget https://raw.githubusercontent.com/joinmisskey/bash-install/main/update.ubuntu.sh -O update.sh
```
```
sudo bash update.sh
```
- 使用 systemd 的小伙伴, 添加 -r 可以更新并重启系统。
- 使用 docker 的小伙伴, 可以特定软件包版本 repository:tag 来更新。
## 使用docker compose部署
### 环境
- git
- docker
- nginx
### 步骤
#### git克隆仓库
```
cd /opt
git clone -b master https://github.com/misskey-dev/misskey.git
cd misskey
git checkout master
```
#### 复制配置文件：
```
cp .config/example.yml .config/default.yml
cp .config/docker_example.env .config/docker.env
cp docker-compose.yml.example docker-compose.yml
```
#### 编辑default.yml中

`url`设置为实例域名
db:`host`设置为`db`
redis:`host`设置为`redis`
#### 构建镜像
```
docker compose build
docker compose run --rm web yarn run init
```
完成之后
#### 启动容器
```
docker compose up -d
```
#### 反向代理
参考以下
```
map $http_upgrade $connection_upgrade {
    default upgrade;
    ''      close;
}

proxy_cache_path /tmp/nginx_cache levels=1:2 keys_zone=cache1:16m max_size=1g inactive=720m use_temp_path=off;

server {
    listen 80;
    listen [::]:80;
    server_name misskey.example.com;
    client_max_body_size 0;

    location / {
        proxy_pass http://127.0.0.1:3000;
        proxy_set_header Host $host;
        proxy_http_version 1.1;
        proxy_redirect off;

        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto https;

        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection $connection_upgrade;

        proxy_cache cache1;
        proxy_cache_lock on;
        proxy_cache_use_stale updating;
        add_header X-Cache $upstream_cache_status;
    }
}
```