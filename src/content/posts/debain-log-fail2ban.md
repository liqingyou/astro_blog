---
title: debain 安装使用 fail2ban
published: 2024-08-20
description: debain 安装使用 fail2ban
tags: [Debain, Log, fail2ban]
category: Debain
draft: false
---

在 Debian 12 上设置登录失败后禁用 IP 可以通过使用 fail2ban 工具来实现。以下是设置步骤：

1. 安装 fail2ban：

```
sudo apt update
sudo apt install fail2ban
```

2. 配置 fail2ban：

创建一个自定义配置文件：

```
sudo nano /etc/fail2ban/jail.local
```

3. 在文件中添加以下内容：

```
[sshd]
enabled = true
port = ssh
filter = sshd
logpath = /var/log/auth.log
maxretry = 3
bantime = 1200
```

这个配置表示：
- 启用 SSH 保护
- 监控 SSH 端口
- 使用 sshd 过滤器
- 监控 /var/log/auth.log 日志文件
- 允许最多 3 次失败尝试
- 禁止时间为 600 秒（10 分钟）

4. 保存并关闭文件。

5. 重启 fail2ban 服务：

```
sudo systemctl restart fail2ban
```

6. 检查 fail2ban 状态：

```
sudo systemctl status fail2ban
```

7. 查看 fail2ban 日志：

```
sudo tail -f /var/log/fail2ban.log
```

这样设置后，如果有 IP 在短时间内多次尝试登录失败，它将被自动禁止一段时间。

注意：你可以根据需要调整 maxretry（最大尝试次数）和 bantime（禁止时间）的值。

如果你想对其他服务也进行类似的保护，可以在配置文件中添加相应的部分。例如，对于 Apache 的保护：

```
[apache]
enabled  = true
port     = http,https
filter   = apache-auth
logpath  = /var/log/apache2/error.log
maxretry = 3
bantime  = 600
```

记得在修改配置后重启 fail2ban 服务以使更改生效。

:::note
可能出现错误 iptable 没有时
:::

配置 fail2ban 使用 nftables（推荐）：

a. 编辑 /etc/fail2ban/jail.local：
```
sudo nano /etc/fail2ban/jail.local
```

b. 将 banaction 设置为 nftables：
```
banaction = nftables-multiport
```
c. 确保你有 nftables 包：
```
sudo apt install nftables
```

重启 fail2ban：

```
sudo systemctl restart fail2ban
```
检查 fail2ban 状态：

```
sudo systemctl status fail2ban
```
再次查看日志以确保错误已解决：

```
sudo tail -f /var/log/fail2ban.log
```
使用 `nftables` 是更现代和推荐的方法，因为它是 Debian 12 的默认防火墙工具。但如果你更熟悉 iptables，也可以选择安装和使用它。

如果问题仍然存在，可能需要检查 fail2ban 服务的环境变量和权限，确保它能够正确访问和执行所需的命令。