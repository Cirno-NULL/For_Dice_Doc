# CentOs

## 防火墙

### 开放端口

```text
firewall-cmd --zone=public --add-port=80/tcp --permanent
```

### 开启/关闭/重启防火墙

```text
systemctl start firewalld
systemctl stop firewalld
systemctl restart firewalld
```

