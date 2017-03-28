一般的什么快捷键，技巧的文章也有很多。我也看过很多。下面这些事我在来自国外大神发布的：[Android Studio Tips of the Day](https://plus.google.com/u/0/collection/wtO0PB)查看到的，而且对于我来说有帮助的及没用过的。

[Android Studio Tips of the Day](https://plus.google.com/u/0/collection/wtO0PB)里面一共有八十几个。大家可以去查看完整的。而且是持续更新状态中。很有用（记得安全上网，翻墙哦。）

------

1.tools:attribute
如果你需要查看写的TextView在有文字时候的预览情况。那么这个就是为你准备的。使用`'tools:something="value"'`这个值会显示在预览时候，但是在软件真正运行的时候不会出现这个内容。
只需要二步就可以：

- 在根布局中添加`xmlns:tools="http://schemas.android.com/tools"`


- 在TextView中使用`'tools:something="value"'`属性

（这个太有用了！！！我以前每次写布局预览效果都用android:text = "XXX",然后程序弄完还得去删。太傻了！！！）

toolsnamespace

2.Extract Resource
比如你在布局文件或者代码文件中直接写了某个String字符串或者某个dimen数值，而不是引用资源文件，那难道还要我再去打开相应的String.xml或者dimen.xml文件去添加，然后这边的布局文件或者代码文件中再去修改使用引用？答案当然是NO。
Mac:选中那个值，然后option+enter键选择Extract String/Dimension Resource 。
Win: alt+enter键选择Extract String/Dimension Resource 。

extractstring

3.Toggle between text/design mode
你可以在OSX用Control + Shift +左/右和在Windows和Linux上用ALT + SHIFT +左/右。来进行Design查看和Text编辑之间切换

![img](http://upload-images.jianshu.io/upload_images/1529568-9a9d65536edc2b1a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

4.CamelHumps
在"Editor->General->Smart Keys"中启动"CamelHumps"功能选项，就可以在连在一起的几个大写为首的单词间快速切换。Mac上是option+左右键。win上为 "alt" or "ctrl" 键。（这里会有个bug,开启后，比如你的变量名是几个单词，比如是isSuccess,这时候你双击想选中这个变量就发现不能全部选中，就变成选中Success了。）

camelhumps

5.Close Others
当Android Studio开了很多文件，想要留下当前文件，然后关闭其他文件，通常做法是右键，然后选择Close Others。实际上只需要
Mac:按住option，然后鼠标点击要留下来的文件的关闭按钮，然后其他的就都关闭了
Win:按住alt.

closeothers

6.The Navigation Bar
导航栏是在IDE顶部的“面包屑”。
这表明你的路径添加到当前文件，但你也可以用它来导航和/或采取对文件和文件夹的操作。

- 您可以导航到父母的子文件夹或找到兄弟类
- 您可以轻松地创建使用代码生成快捷方式（CMD + N / ALT +插入）新文件
- 事实上，你可以在项目视图通过右键点击做任何事情
- 你可以隐藏这个导航栏。通过快捷键来显示。可以让Android Studio的屏幕显示内容可以更多。

navigationbar

7.Open Source in New Window
你能让当前打开的文件，以另起一个窗口来进行显示。
Mac:shift +F4（有些人F4可能是系统快捷键，那就多加一个fn）
Win:shift+F4

opensourceinnewwindow

8.Override Methods
我们可能想重载某个父类的方法，但是一时间忘记了这个方法的名字，可以快捷键调出所有可重载的方法，进行选择。
Mac:control + o
Win:ctrl + o

overridemethod

9.Edit Regex
描述：使用Java编写正则表达式是一件很困难的事，主要原因是：

- 你必须得避开反斜杠；
- 说实话，正则很难；
- 看第二条。
  IDE能帮我们干点啥呢？当然是一个舒服的界面来编写和测试正则啦~ - 快捷键：Alt + Enter → check regexp

checkregexp

10.The Switcher
打开的文件太多。怎么快速切换文件？
Mac : control + tab
win: ctrl + tab

![img](http://upload-images.jianshu.io/upload_images/1529568-0138bef23f2ea38b.gif?imageMogr2/auto-orient/strip)