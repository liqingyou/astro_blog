---
title: 【docker】私有IM | Matrix的部署与使用
published: 2024-08-19
description: 【docker】私有IM | Matrix的部署与使用
tags: [Matrix, Docker]
category: Docker
draft: false
---

1. 创建文件夹
```
mkdir -p /root/data/docker_data/matrix/data
cd /root/data/docker_data/matrix
```

2. 生成默认配置
```
docker run -it --rm \
    -v /opt/develop/projects/matrix/data:/data \
    -e SYNAPSE_SERVER_NAME=im.linkscar.com \
    -e SYNAPSE_REPORT_STATS=no \
    matrixdotorg/synapse:latest generate
```

3. 添加注册功能
修改文件 `homeserver.yaml`
```
enable_registration: true
enable_registration_without_verification: true
```

4. 使用 docker compose 启动
创建文件 `docker-compose.yml`
```
version: "3.3"
 
services:
  synapse:
    image: "matrixdotorg/synapse:latest"
    container_name: "matrix_synapse"
    restart: unless-stopped
    ports:
      - 8008:8008
    volumes:
      - "./data:/data"
    environment:
      VIRTUAL_HOST: "matrix.yemengstar.com"
      VIRTUAL_PORT: 8008
      LETSENCRYPT_HOST: "matrix.yemengstar.com"
      SYNAPSE_SERVER_NAME: "matrix.yemengstar.com"
      SYNAPSE_REPORT_STATS: "yes"
```

修改权限
```
chown -R 991:991 /root/data/docker_data/matrix/data
```

运行
```
docker-compose up -d
```