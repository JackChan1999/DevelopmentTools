如何安装插件详见：[https://packagecontrol.io/installation](https://packagecontrol.io/installation)

1. [Alignment](http://wbond.net/sublime_packages/alignment)：选中并按`ctrl+alt+a`就可以使其按照等号对其。
   ![img](http://upload-images.jianshu.io/upload_images/26219-b4dcc90c37386703.gif?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240/format/jpg)
   按等号对其，强迫症患者必备
2. [C Improved](https://github.com/abusalimov/SublimeCImproved)：更加人性化的C语言着色方案。
   ![img](http://upload-images.jianshu.io/upload_images/26219-1f7df1e499c496ff.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240/format/jpg)
   着色对比，还不错
   ![img](http://upload-images.jianshu.io/upload_images/26219-9c1425440dcbf67f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240/format/jpg)
   最好设置为默认用C Improved打开C文件
3. [CoolFormat](http://akof1314.github.io/CoolFormat/)：简单好用的代码格式化工具，相当于简化版的Astyle，默认`ctrl+alt+shift+q`格式化当前文件，`ctrl+alt+shift+s`格式化当前选中。
   ![img](http://upload-images.jianshu.io/upload_images/26219-84e77c9279cea776.gif?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240/format/jpg)
   默认选中按`ctrl+alt+shift+s`格式化当前
   **注**：格式的设置可以打开控制面板，输入CoolFormat : Formatter Setting，C/C++文档参考[此处](http://akof1314.github.io/CoolFormat/doc/Cpp.html)
   ![img](http://upload-images.jianshu.io/upload_images/26219-608f1e8315a138a4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240/format/jpg)
   控制面板相关命令
4. [DocBlockr](https://github.com/spadgos/sublime-jsdocs)：自动生成大块的注释，并且可以用`tab`在不同内容之间切换，很爽的
   ![img](http://upload-images.jianshu.io/upload_images/26219-318ce98c56fdfe18.gif?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240/format/jpg)
   用`tab`在参数之间平滑切换
   ![img](http://upload-images.jianshu.io/upload_images/26219-9a58baaa98020b35.gif?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240/format/jpg)
   当然，不在函数上面也可以比较方便的生成注释块
   **注**：安装完重启一下，否则可能效果不理想，比如`tab`跳到别的地方去了
5. [AllAutocomplete](https://github.com/alienhard/SublimeAllAutocomplete)：Sublime自带的可以对当前文件中的变量和函数名进行自动提示，但是AllAutocomplete可以对打开的所有文件的变量名进行提示，增强版的代码自动提示符。Extend Sublime autocompletion to find matches in all open files of the current window
6. [CTags](https://github.com/SublimeText/CTags)：可以在函数的声明和定义自检来回跳转了，首先需要[下载Ctags](http://ctags.sourceforge.net/)，比如我存在D盘的根目录下，之后需要在Sublime中配置路径。
   ![img](http://upload-images.jianshu.io/upload_images/26219-4f4e8d14aa88cd6d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240/format/jpg)
   Ctags路径设置
   然后在工程文件夹的右键生成索引文件，
   ![img](http://upload-images.jianshu.io/upload_images/26219-e470313552177d55.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240/format/jpg)
   为工程文件夹内的文件生成索引
   然后就可以用`ctrl+shift+左键`跳转到定义处了，`ctrl+shift+右键`回来了（不过，还是没有Source Insight方便，可以实时小窗口预览）
   ![img](http://upload-images.jianshu.io/upload_images/26219-b2de253cebf75665.gif?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240/format/jpg)
   跳过来跳过去
7. [SublimeAStyleFormatter](http://theo.im/SublimeAStyleFormatter/)：国人做的Astyle Sublime版，蛮不错的。
   安装完成之后，下面这个配置一定要打开，即保存自动格式化，这个相比于CoolFormat要简单很多。
   ![img](http://upload-images.jianshu.io/upload_images/26219-4823e065b8152fbd.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240/format/jpg)
   保存自动格式化配置
   ![img](http://upload-images.jianshu.io/upload_images/26219-1a1003423f2138c1.gif?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240/format/jpg)
   按`ctrl+s`保存的同时自动格式化当前文件
8. [Cscope](https://github.com/ameyp/CscopeSublime)：TBC
   参考:[https://www.zybuluo.com/lanxinyuchs/note/33551](https://www.zybuluo.com/lanxinyuchs/note/33551)[http://hwchiu.logdown.com/posts/174922-sublime-text-3-cscope](http://hwchiu.logdown.com/posts/174922-sublime-text-3-cscope)

**Sublime Text 系列**

- [Sublime Text：学习资源篇](http://www.jianshu.com/p/d1b9a64e2e37)
- [Sublime插件：增强篇](http://www.jianshu.com/p/5905f927d01b)
- [Sublime插件：Markdown篇](http://www.jianshu.com/p/aa30cc25c91b)
- [Sublime插件：C语言篇](http://www.jianshu.com/p/595975a2a5f3)
- [Sublime插件：主题篇](http://www.jianshu.com/p/13fedee165f1)
- [Sublime插件：Git篇](http://www.jianshu.com/p/3a8555c273d8)
- [Sublime 小技巧：文本自动换行显示？](http://www.jianshu.com/p/c75d21d2e967)