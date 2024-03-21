---
title: 部署Caddy2，快速配置反向代理
date: 2024-03-21 14:15:02
thumbnail: "https://p.ananas.chaoxing.com/star3/origin/cef4d6a3b69fe79ce8f3c96cdca225cd.webp"
excerpt: false
categories:
- 网站
tags:
- Web
---

#### 安装Caddy2
```bash
sudo apt install -y debian-keyring debian-archive-keyring apt-transport-https
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/gpg.key' | sudo gpg --dearmor -o /usr/share/keyrings/caddy-stable-archive-keyring.gpg
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/debian.deb.txt' | sudo tee /etc/apt/sources.list.d/caddy-stable.list
sudo apt update
sudo apt install caddy
```

#### 编辑Caddyfile文件
```bash
vi /etc/caddy/Caddyfile
```

#### 配置反向代理
```bash
xx.xx.xx{
    reverse_proxy localhost:8000
}
```

#### 其他Caddy命令
```bash
systemctl enable caddy.service   # 开机启动
systemctl start caddy.service    # 启动
systemctl stop caddy.service     # 停止
systemctl restart caddy.service  # 重启
systemctl status caddy.service   # 查看状态
systemctl daemon-reload          # 重载配置
```