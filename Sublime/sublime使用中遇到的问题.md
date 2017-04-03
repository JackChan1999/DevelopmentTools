---
typora-copy-images-to: img
---

## 侧边栏

view → side bar → show side bar（显示）

## package control 

There are no packages available for installation

![package control](img/packagecontrol.png)

```
Package Control: Attempting to use Urllib downloader due to WinINet error: Error downloading channel. (errno 12152) during HTTP write phase of downloading https://packagecontrol.io/channel_v3.json.
Package Control: Error downloading channel. URL error [WinError 10060] 由于连接方在一段时间后没有正确答复或连接的主机没有反应，连接尝试失败。 downloading https://packagecontrol.io/channel_v3.json.
```

解决方法：http://www.jianshu.com/p/a3af44257b15

## vim命令

sublime text实现vim命令格式（Vintage插件是自带的插件，默认是忽略掉的）

![img](http://images.cnitblog.com/blog/276015/201412/012109255761686.jpg)

选择，setting user下，添加一条命令：

```
"ignored_packages": []

在default设置模式下，忽略了Vintage插件，因为在sublime text3下默认配置文件不支持修改，所以只能在用户配置下覆盖掉那一项设置了。
//这条命令是把默认模式修改为命令行模式
"vintage_start_in_command_mode": true
```



## 如何优雅的使用Sublime Text

http://jeffjade.com/2015/12/15/2015-04-17-toss-sublime-text/

