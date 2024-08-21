---
title: debain log 监控 
published: 2024-08-20
description: debain log 监控 
tags: [Debain, Log]
category: Debain
draft: false
---

1. Install Rsyslog (if not installed): 安装
```
sudo apt update
sudo apt install rsyslog
```

2. 
    - 创建或者编辑
    ```
    sudo nano /etc/rsyslog.d/50-default.conf
    ```

    - 填入以下内容
    ```
    auth,authpriv.* /var/log/auth.log
    ```

3. 重启服务
```
sudo systemctl restart rsyslog
```

4. 查看日志
```
sudo cat /var/log/auth.log
```