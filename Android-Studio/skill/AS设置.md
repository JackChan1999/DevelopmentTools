---
typora-copy-images-to: img
---

## 禁用Windows中Ctrl+Space切换输入法的快捷键

Windows的Ctrl+Space快捷键（切换中文输入法）跟一堆IDE的冲突，所以必须禁用掉，按照下图那样修改注册表即可。还好我用的eclipse快捷键不用修改.

![](img/as1.png)

## 修改idea.properties文件

找到&lt;android-studio>\bin\idea.properties文件，打开，改成这样：

![](img/as2.png)
```
# 禁止第一次运行Android Studio时，自动检查和升级Android SDK
disable.android.first.run=true
# 下面两个是Android Studio的设置、插件和运行时产生的其他文件存放的目录
# 不改的话，Windows中默认在 C:\Users\<username>\.AndroidStudio.2\ 里面
# ${idea.home.path}表示Android Studio程序的主目录，注意目录分隔符要用正斜杠“/”
idea.config.path=${idea.home.path}/.AndroidStudio.2/config
idea.system.path=${idea.home.path}/.AndroidStudio.2/system
```
## 设置主题,窗口大小,动画效果

- 修改主题
- 修改全局窗口字体(需要选择中文字体,最好默认不做修改),字号
- 窗口动画(电脑性能不怎样可以禁止掉)

![](img/as3.png)

## 修改menu或者toolBar

这里我是添加了创建class,fragment,activity的ToolBar,这个根据个人情况

![1493706327626](img/1493706327626.png)

![](img/as4.png)

## 打开工程设置

- 禁用自动打开上次关闭工程 ,禁用退出提示  
- 打开新项目提示方式

![](img/as5.png)

## 设置网络代理

配置红杏公益代理.

![](img/as6.png)

## 禁用自动检查更新

取消自动更新

![](img/as7.png)

## 配置快捷键

1. 自定义快捷键
2. 根据内容搜索快捷键
3. 根据按键搜索快捷键
4. 删除快捷键

![](img/as8.png)

## 编辑器

1. 鼠标悬停显示文档 
2. 格式化&导包提示

![](img/as9.png)

鼠标指针悬停若干时间，显示文档，时间自己改。就是按格式化代码或者导包时，是否会显示个对话框，觉得烦人的话，都取消掉吧

## 显示行号，显示方法分隔线

①显示行号 ②显示方法分隔符

![](img/as10.png)

## 代码折叠

①取消方法自动折叠

![](img/as11.png)

## 代码智能提示

① 敲什么都提示②③提示时间设置

![](img/as12.png)

敲什么字符会提示，All(大小写全部符合)，None（不管大小写，符合就提示），（First letter）（第一个字符符合就OK，其他随意）。我这种脑残没记性的当然选择None。时间设置根据自己电脑性能.

## 自动导包

![](img/as13.png)

Optimize imports on the fly：优化导包，格式化代码时会删掉多余的导包。Add unambiguous imports on the fly：敲代码时，敲简单类名就帮你把包导了。

## 创建个人代码样式配置

估计是为了保护默认的代码样式配置，让用户把配置搞坏了也能一键还原，IDEA不允许修改默认的配置，需要用户创建配置才能进行修改。选择基于哪个主题的，然后Save As一份即可。

![](img/as14.png)

## 修改代码字体

强烈建议用Consolas字体，好看！！！

![](img/as15.png)

## 修改控制台字体

![](img/as16.png)

## Logcat字体

要改的话，得先把1那个地方的勾取消掉,默认android Logcat 每个级别的颜色都是一样的.建议修改

![](img/as17.png)

## 修改注释位置

禁用“语句堆一行”

![](img/as18.png)

Comment at frist column：启用的话，注释符号就会在行首，否则就按照缩进来注释。Control statement in one line：格式化代码的时候，会把些很短的语句合并成一行。这样影响代码可读性.

## 修改变量前后缀

静态成员是s，普通成员是m，转换成成员变量的时候自动加上m,生成setter,getter的时候会忽视m,很好很强大.

![](img/as19.png)

## 取消Android Lint 检查

一定程度加快速度吧

![](img/as20.png)

## 修改新建文件文件头

每次建新类,会加上这样的头信息

![](img/as21.png)

上图就是通用的文件头，框住的地方是你系统的用户名，想个性化的话，可以改这里，至于哪里引用这个文件头的呢，就在隔壁。

![](img/as22.png)

## 修改文件编码为UTF-8

![](img/as23.png)

别坑队友，小伙伴们都统一改为UTF-8吧。

## 自己定义Live Templates

模板定义,方便开发,减少重复代码

![](img/as24.png)

## 添加管理插件

![](img/as25.png)

## Svn添加移除项目

![](img/as26.png)

## 配置Svn安装路径

![](img/as27.png)

## Github账号绑定

![](img/as28.png)

## 配置git安装路径

![](img/as29.png)

## 配置Gradle安装路径,离线模式,本地Gradle仓库

![](img/as30.png)

## 配置maven仓库路径

![](img/as31.png)

## 项目自动编译

![](img/as32.png)

## Gradle Task超时时间

![](img/as33.png)

## 优化-取消同步

![](img/as34.png)

## 优化-提供构建速度

![](img/as35.png)
