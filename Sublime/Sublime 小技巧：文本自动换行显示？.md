> 题记：虽然现在写代码时，一般各种语言的规范都会说写一行代码不要超过好多好多字，如PEP8是79个字符，以便于阅读。但是，有时候还是需要的，如看log，文档等。

有人喜欢默认显示这样的：（强迫症患者）

自动换行显示

也有人喜欢默认显示成那样的：（随心所欲者）

单行显示

也有人喜欢一会这样，一会那样的。（不折腾会死星人）

so Sublime 可以通过设置**配置**，**快捷键**和**插件**满足各种不同的需求。

## 配置

如果想默认打开文件即换行显示，在选项配置中设置`word_wrap`为`true`即可

```
{
    "word_wrap": true
}
```

如果想默认打开文件即单行显示，在选项配置中设置`word_wrap`为`false`即可

```
{
    "word_wrap": false
}
```

## 快捷键

我们可以通过鼠标点击`View` -> `Word Wrap`来选中自动换行显示或者单行显示；自然也可以通过配置快捷键来实现快速的切换，如下设置`ctrl+shift+w`在是否 `Word Wrap`之间进行切换（toggle）

```
[
    { "keys": ["ctrl+shift+w"], "command": "toggle_setting", "args": {"setting": "word_wrap"}}
]
```

注：修改完快捷键配置无需重启，即刻生效，并且会在菜单上显示所配置的快捷键，很是贴心。

## 插件

Sublime 上真是啥插件都有，有人就做了个[增强版](https://github.com/ehuss/Sublime-Wrap-Plus)，可以制定好多列换行显示的。

这个有点过分了，就不折腾了，，，

## 参考

- [How to set shortcut for menu “View => word Wrap”?](https://forum.sublimetext.com/t/how-to-set-shortcut-for-menu-view-word-wrap/5278)
- [QUICK TIP: ENABLE SUBLIME TEXT WORD WRAP](http://justinseeley.com/tutorials/quick-tip-enable-sublime-text-word-wrap/)
- [Sublime - Key Binding for Toggle Word Wrap](http://commonmanrants.blogspot.sg/2014/04/sublime-key-binding-for-toggle-word-wrap.html)
- [Sublime-Wrap-Plus](https://github.com/ehuss/Sublime-Wrap-Plus) : Enhanced "wrap lines" command for Sublime Text 2 or 3.

**Sublime Text 系列**

- [Sublime Text：学习资源篇](http://www.jianshu.com/p/d1b9a64e2e37)
- [Sublime插件：增强篇](http://www.jianshu.com/p/5905f927d01b)
- [Sublime插件：Markdown篇](http://www.jianshu.com/p/aa30cc25c91b)
- [Sublime插件：C语言篇](http://www.jianshu.com/p/595975a2a5f3)
- [Sublime插件：主题篇](http://www.jianshu.com/p/13fedee165f1)
- [Sublime插件：Git篇](http://www.jianshu.com/p/3a8555c273d8)
- [Sublime 小技巧：文本自动换行显示？](http://www.jianshu.com/p/c75d21d2e967)