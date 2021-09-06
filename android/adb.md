# adb

| 系统界面 | 指令 |
| :--- | :--- |
| 进入adb | adb shell    \|   adb start-server |
| 强制卸载系统软件 | pm uninstall -k --user 0 软件包名 |
| 系统进入9008\(大部分无效\) | adb reboot edl |

| fastboot | 指令 |
| :--- | :--- |
| fastboot进入9008\(大部分无效\) | fastboot oem edl |
| fastboot进入9008\(大部分无效\) | fastboot reboot emergency |
| 刷入boot.img\(没解锁无效\) | fastboot flash boot boot.img |
| 刷入recovery\(没解锁无效\) | fastboot flash recovery recovery.img |

| 9008 | 暂无 |
| :--- | :--- |
| 9008目前只会使用工具 | 暂时还没接触到指令操作 |

## 修改分辨率

```text
shell wm size
#显示大小
shell wm size reset
#重置大小
shell wm size 1024x1024
#设置大小
```

## 查看端口

### 查看所有端口

```text
adb shell netstat
```

### 查看指定端口

```text
adb shell netstat -ano | findstr 5037
```

## 查看设备

```text
adb devices
```

## apk安装卸载查看

### 安装apk

```text
adb install apk
adb install -r apk
adb -s device install apk
adb -s device install -r apk
```

### 查看已安装apk

```text
adb shell 
cd /data/app
ls
exit


adb shell pm list package
```

### 卸载apk

```text
adb unstall apkname
adb shell pm uninstall -k --user 0 软件包名
```

## 文件上传下载

### 文件上传

```text
adb push localFile devicesPath
adb push C:\Users\Administrator\Desktop\1.txt /sdcard
```

### 文件下载

```text
adb pull devicesFile localPath
adb pull /sdcard/server.log C:\Users\Administrator\Desktop\
note:不能直接下载到本地磁盘根目录
```

## Logcat

Logcat日志

* 严重程度serverity   
* 优先级priority   

V verbose累赘  
D debug  
I info  
W warn  
E error  
F fatal致命  
S silent沉默

```text
adb logcat -help
adb logcat 打印默认日志数据 

adb logcat *:E 打印级别为Error的信息
adb logcat > C:\Users\Administrator\Desktop\log.txt 
日志保存到本地
adb logcat >> C:\Users\Administrator\Desktop\log.txt 
日志附加到本地
```

## monkey随机测试

### 基础示例

```text
adb shell monkey [options] <event-count>

adb shell monkey   
--throttle 1000     间隔时间
-p appname          指定包名
-s 10               种子值
-v -v -v            log级别,一个-v一个级别
1000                次数
使用时写成一行
```

### 事件代码

| 事件代码 | 事件名称 |
| :--- | :--- |
| --pct-touch | 触摸事件百分比 |
| --pct-motion | 滑动事件百分比 |
| --pct-pinchzoom | 缩放事件百分比 |
| --pct-trackball | 轨迹球事件百分比 |
| --pct-rotation | 屏幕旋转事件百分比 |
| --pct-nav | 基本导航事件百分比 |
| --pct-majornav | 主要导航事件百分比 |
| --pct-syskeys | 系统事件百分比 |
| --pct-appswitch | Activity启动事件百分比 |
| --pct-flip | 键盘事件百分比 |
| --pct-anyevent | 其他事件百分比 |

### 整合示例

```text
adb shell monkey --pct-touch  50  -p  com.taobao.taobao -v 1000
adb shell monkey --pct-motion  70  -p  com.taobao.taobao  -v -v 1000
```

