这是从Philippe Breault的系列文章《Android Studio Tips Of the Day》中提取出来的自认为精华的部分。这些技巧在实际应用中能够非常大的提高工作效率。

## 关于快捷键

### The File Structure Popup

`ctrl+f12`
此快捷键可以调出当前文件的大纲，并通过模糊匹配快速跳转至指定的方法。
勾选上“show anonymous classes”后其功能相当于Eclipse中的ctrl+o

[![10-8-1](http://jbcdn2.b0.upaiyun.com/2015/10/24a4c0afd78ed617ea05a469f9fbf9fd.gif)](http://jbcdn2.b0.upaiyun.com/2015/10/24a4c0afd78ed617ea05a469f9fbf9fd.gif)

### The Call Hierarchy Popup

`ctrl+alt+h`
查看某个方法的调用路径。
[![10-8-2](http://jbcdn2.b0.upaiyun.com/2015/10/387316c17c8827272b38f413b097d9f2.gif)](http://jbcdn2.b0.upaiyun.com/2015/10/387316c17c8827272b38f413b097d9f2.gif)

### Quick Definition Lookup

`ctrl+shift+i`
不离开当前文件当前类的情况下快速查看某个方法或者类的实现。通过大概预览下调用的方法，可以避免许多未知的坑。
[![10-8-3](http://jbcdn2.b0.upaiyun.com/2015/10/41b81d385da6bcb7cb6795874ac53b2a.gif)](http://jbcdn2.b0.upaiyun.com/2015/10/41b81d385da6bcb7cb6795874ac53b2a.gif)

### Bookmarks!

如其名，书签。帮助快速回到指定的位置，实际使用中简直爽得不行。
`f11`
将当前位置添加到书签中或者从书签中移除。

`shift+f11`
显示有哪些书签。

[![10-8-4](http://jbcdn2.b0.upaiyun.com/2015/10/a0c439e82f06b150bdcbb0f5d463b886.gif)](http://jbcdn2.b0.upaiyun.com/2015/10/a0c439e82f06b150bdcbb0f5d463b886.gif)

### Find Actions

`ctrl+shift+a`
对于没有设置快捷键或者忘记快捷键的菜单或者动作（Action），可能通过输入其名字快速调用。神技！！！
例如想要编译，只需要输入”release”，则列表框中就会出现”assembleRelease”选项，选择就可以进行编译。

[![10-8-5](http://jbcdn2.b0.upaiyun.com/2015/10/54f343f081c1ef18cb8476457c181805.gif)](http://jbcdn2.b0.upaiyun.com/2015/10/54f343f081c1ef18cb8476457c181805.gif)

### Move Lines Up/Down

`alt+shift+up/down`
上下移动行，这个没什么好说的，肯定会用到。

[![10-8-6](http://jbcdn2.b0.upaiyun.com/2015/10/40105c58ea950bbdda58123a97a09329.gif)](http://jbcdn2.b0.upaiyun.com/2015/10/40105c58ea950bbdda58123a97a09329.gif)

### Lines Edit

`ctrl+y`，`ctrl+x`, `ctrl+d`
删除行，删除并复制行，复制行并粘贴，必备。

### VCS Operations Popup

`Alt+``(是1左边的那个键)
此快捷键会显示一个版本管理常用的一个命令，可以通过命令前面的数字或者模糊匹配来快速选择命令。
极大的提高了工作效率，快速提交代码、暂存代码、切分支等操作操作如鱼得水。

[![10-8-7](http://jbcdn2.b0.upaiyun.com/2015/10/1d3d2a61f9171e9522cbd68195699e82.gif)](http://jbcdn2.b0.upaiyun.com/2015/10/1d3d2a61f9171e9522cbd68195699e82.gif)

### Hide All Panels

`ctrl+shift+f12`
关闭或者恢复其他窗口。在编写代码的时候非常方便的全屏编辑框，可以更加专心的coding…

[![10-8-8](http://jbcdn2.b0.upaiyun.com/2015/10/3f1c3e5a6aa0662994a4c21d498c659f.gif)](http://jbcdn2.b0.upaiyun.com/2015/10/3f1c3e5a6aa0662994a4c21d498c659f.gif)

### Parameter Info

`ctrl+p`
在调用一些方法的时候免不了会忘记或者不知道此方法需要哪些参数。`ctrl+p`可以显示出此方法需要的参数。必备技能之一。

### Rename

`shift+f6`
重命名变量或者方法名。重构神技。

[![10-8-9](http://jbcdn2.b0.upaiyun.com/2015/10/1f12e8ade7c4030738d8c0380405f309.gif)](http://jbcdn2.b0.upaiyun.com/2015/10/1f12e8ade7c4030738d8c0380405f309.gif)

## 条件断点

通过右键断点，可以对一个断点加入条件。只有当满足条件时，才会进入到断点中。调试神技，只对自己关心的情况进行调试，不浪费时间。

[![10-8-10](http://jbcdn2.b0.upaiyun.com/2015/10/31d5c82d240912172894dd1c09bafea1.gif)](http://jbcdn2.b0.upaiyun.com/2015/10/31d5c82d240912172894dd1c09bafea1.gif)

## 进入调试模式

点击`Attach Debugger`(即绿色小虫旁边那个)可以快速进入调试而不需要重新部署和启动app。
可以选择为此功能设置一个快捷键或者通过前面提到的`Find Actions(ctrl+shift+a)`输入”attach”进行调用。

[![10-8-11](http://jbcdn2.b0.upaiyun.com/2015/10/ede57865082dac483aac632cf9120575.gif)](http://jbcdn2.b0.upaiyun.com/2015/10/ede57865082dac483aac632cf9120575.gif)

## 快速查看变量的值

按住`Alt`点击想要查看的变量或者语句。如果想查看更多，则可以按`Alt+f8`调出`Evaluate Expression`窗口来自行输入自定义的语句。

[![10-8-12](http://jbcdn2.b0.upaiyun.com/2015/10/32b95448a118d41aae4824fc7c9f7fb3.gif)](http://jbcdn2.b0.upaiyun.com/2015/10/32b95448a118d41aae4824fc7c9f7fb3.gif)

## 分析堆栈信息

`Find Actions(ctrl+shift+a)`输入”analyze stacktrace”即可查看堆栈信息。

[![10-8-13](http://jbcdn2.b0.upaiyun.com/2015/10/37d61a0726b23aa9a2d816b31f610ca0.gif)](http://jbcdn2.b0.upaiyun.com/2015/10/37d61a0726b23aa9a2d816b31f610ca0.gif)

## 分析某个值的来源

`Find Actions(ctrl+shift+a)`输入”Analyze Data Flow to Here”，可以查看某个变量某个参数其值是如何一路赋值过来的。
对于分析代码非常有用。

[![10-8-14](http://jbcdn2.b0.upaiyun.com/2015/10/ccd61abf519200d716e1b9389d18912b.gif)](http://jbcdn2.b0.upaiyun.com/2015/10/ccd61abf519200d716e1b9389d18912b.gif)

## 多行编辑

强大的神技之一，用过vim的vim-multiple-cursors或者Sublime Text的多行编辑都不会忘记那种快感！ 也许不是平时用得最多的技能，但是却是关键时刻提高效率的工具。
快捷键：`Alt+J`
[![10-8-15](http://jbcdn2.b0.upaiyun.com/2015/10/252c0bcfef584e695e680004a061bf2f.gif)](http://jbcdn2.b0.upaiyun.com/2015/10/252c0bcfef584e695e680004a061bf2f.gif)

## 列编辑

在vim中叫作块编辑，同样神技！使用方法：按住`Alt`加鼠标左键拉框即可
PS：发现Ubuntu下不可用，代替方法为按`Alt+Shift+Insert`之后拖框选择。
但是经过这么操作之后，神技就大打折扣了。估计是与Ubuntu的快捷键冲突了。

[![10-8-16](http://jbcdn2.b0.upaiyun.com/2015/10/f8a0b2c194dccc053fabbc278aace2bf.gif)](http://jbcdn2.b0.upaiyun.com/2015/10/f8a0b2c194dccc053fabbc278aace2bf.gif)

## Enter和Tab在代码提示时的区别

看图!
[![10-8-17](http://jbcdn2.b0.upaiyun.com/2015/10/21418551eaaceb6a05e79a12f9d9c2be.gif)](http://jbcdn2.b0.upaiyun.com/2015/10/21418551eaaceb6a05e79a12f9d9c2be.gif)

## Links

1. [Android Studio Tips Of the Day – Roundup #1](http://www.developerphil.com/android-studio-tips-of-the-day-roundup-1/)
2. [Android Studio Tips Of the Day – Roundup #2](http://www.developerphil.com/android-studio-tips-of-the-day-roundup-2/)
3. [Android Studio Tips Of the Day – Roundup #3](http://www.developerphil.com/android-studio-tips-of-the-day-roundup-3/)
4. [Android Studio Tips Of the Day – Roundup #4](http://www.developerphil.com/android-studio-tips-of-the-day-roundup-4/)
5. [Android Studio Tips Of the Day – Roundup #5](http://www.developerphil.com/android-studio-tips-of-the-day-roundup-5/)
6. [Android Studio Tips Of the Day – Roundup #6](http://www.developerphil.com/android-studio-tips-of-the-day-roundup-6/)