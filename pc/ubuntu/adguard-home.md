# Adguard Home

## 下载安装

```text
curl -s -S -L https://raw.githubusercontent.com/AdguardTeam/AdGuardHome/master/scripts/install.sh | sh -s -- -v
```

## 启动停止等

```text
sudo /opt/AdGuardHome/AdGuardHome -s start|stop|restart|status|install|uninstall
```

用到的一些教程,实验中

## 一些问题

### listen udp 0.0.0.0:53: bind: address already in use

解决方法:[链接](https://github.com/AdguardTeam/AdGuardHome/wiki/FAQ#bindinuse)

实际我用的解决方法：

```text
第一种
lsof -i:53
出来了一大堆的named的玩意，pid是606
kill 606

第二种
sudo netstat -anlp | grep -w LISTEN
sudo systemctl stop named

暂时不知道哪种方法更ok一点
所以全用上了，能用就行.jpg
```

