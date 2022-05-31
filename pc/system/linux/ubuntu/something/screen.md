# Screen

## # 官方手册

[官方手册](http://www.gnu.org/software/screen/manual/screen.html)

## 个人常用Screen指令

### 查看screen列表

```
screen -ls
```

### 进入screen

```
screen -r screen名称
```

### 退出screen

```
Ctrl+a d
```

### 强制创建screen并命名

```
screen -dmS screen名称
```

### 强制关闭screen
```
screen -S screen名称 -X quit
```
