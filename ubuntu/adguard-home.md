# Adguard Home

### 下载安装

```text
curl -s -S -L https://raw.githubusercontent.com/AdguardTeam/AdGuardHome/master/scripts/install.sh | sh -s -- -v
```

### 启动停止等

```text
sudo /opt/AdGuardHome/AdGuardHome -s start|stop|restart|status|install|uninstall
```

用到的一些教程,实验中

### 一些问题

#### listen udp 0.0.0.0:53: bind: address already in use

解决方法:[链接](https://github.com/AdguardTeam/AdGuardHome/wiki/FAQ#bindinuse)

实际我用的解决方法：

```text
lsof -i:53
kill pid
```



