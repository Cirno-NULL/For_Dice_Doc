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

