---
title: Wazuh Docker 部署
published: 2024-08-14
description: Wazuh Docker 部署
tags: [Wazuh, Docker]
category: Wazuh
draft: false
---

执行以下命令以获取所需的证书：
```
docker-compose -f generate-indexer-certs.yml run --rm generator
```

启动
```
docker-compose up -d
```

Wazuh 仪表板的默认用户名和密码是 admin 和 SecretPassword。为了提高安全性，您可以更改 Wazuh 索引器管理员用户的默认密码。



```
sudo systemctl daemon-reload
sudo systemctl enable wazuh-agent
sudo systemctl start wazuh-agent
```

参考链接:
1. [Wazuh Docker 部署](https://documentation.wazuh.com/current/deployment-options/docker/wazuh-container.html)