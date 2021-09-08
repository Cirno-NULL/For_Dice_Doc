# CentOs

## 防火墙
### 开放端口
```shell
firewall-cmd --zone=public --add-port=80/tcp --permanent
```
### 开启/关闭/重启防火墙
```
systemctl start firewalld
systemctl stop firewalld
systemctl restart firewalld
```