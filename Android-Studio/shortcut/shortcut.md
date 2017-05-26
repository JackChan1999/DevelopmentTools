---
typora-copy-images-to: img
---

## 常用快捷键

![](img/快捷键.jpg)

| 快捷键                | 功能说明                                     |
| :----------------- | :--------------------------------------- |
| Alt + shift + R    | Rename，重命名                               |
| Ctrl + shift + o   | 导包                                       |
| Ctrl + shift + F   | 格式化代码                                    |
| Ctrl + shift + /   | 注释一段代码(/**/)                             |
| Ctrl + /           | 注释代码(//)                                 |
| Ctrl + alt + f     | 将变量提升为全局变量                               |
| Ctrl + alt + v     | 快速创建局部变量                                 |
| Alt + insert       | 快速插入：constructor，setter，getter，equals，tostring，hashcode，  Override method… |
| Alt + enter        | 快速修复：强制类型转换，实现接口方法，导包                    |
| Alt + P            | 方法参数提示                                   |
| Ctrl + K           | 选中变量，快速跳到下一个                             |
| Ctrl + F           | 搜索或替换                                    |
| Ctrl + H           | 查找 + 替换                                  |
| Alt + 鼠标右键         | 列编辑                                      |
| Alt + 方向上/下        | 移动一行代码                                   |
| Ctrl + alt + 方向上/下 | 复制一行代码                                   |
| Ctrl + Y           | 恢复                                       |
| Ctrl + X           | 剪切                                       |
| Ctrl + D           | 删除                                       |
| Ctrl + C           | 复制一行代码                                   |
| F4                 | 查看类的继承机构                                 |
| Ctrl + O           | 显示一个的成员：成员变量，方法                          |
| Ctrl + Shift + T   | 查找类                                      |

Ctrl + F4 关闭类

shift + esc 隐藏侧边栏

Alt + 1 显示隐藏工程面板

Alt + 7 显示隐藏Structure面板

![1493270882232](img/1493270882232.png)

![](img/shortcut.jpg)

## Ctrl + Shift + T 查找类

![](http://img.blog.csdn.net/20170305222602447?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvYXhpMjk1MzA5MDY2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

## Ctrl + Shift + R 查找文件

![1495545677617](img/1495545677617.png)

## Ctrl + O 

显示一个类的成员：成员变量，方法，输入方法名可以快速定位到方法位置

![](http://img.blog.csdn.net/20170305222653197?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvYXhpMjk1MzA5MDY2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

## F4 显示类的继承结构

![](http://img.blog.csdn.net/20170305223537159?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvYXhpMjk1MzA5MDY2/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

## 查找功能

### 1. 在当前窗口查找文本【Ctrl+F】

![这里写图片描述](http://img.blog.csdn.net/20160913145240075)
F3 向下查找关键字出现位置 
Shift+F3 向上一个关键字出现位置

### 2. 在当前工程内查找文本【Ctrl+Shift+F】

先会弹出一个对话框，直接点击【find】，开始在整个工程内查找该字符串 
![这里写图片描述](http://img.blog.csdn.net/20160913145844499) 
查找结果如下： 
![这里写图片描述](http://img.blog.csdn.net/20160913150015344)

### 3. 查找类【Ctrl+N】

![这里写图片描述](http://img.blog.csdn.net/20160913161110599)

### 4. 查找文件【Ctrl+Shift+N】

![这里写图片描述](http://img.blog.csdn.net/20160913161212756)

### 5. 查找项目中的方法或变量【Ctrl+Shift+Alt+N】

![这里写图片描述](http://img.blog.csdn.net/20160913163700918)

### 6. 查找类/方法/变量引用的地方

先定位光标

![这里写图片描述](http://img.blog.csdn.net/20160921172257716)

右键选择“Find Usages”（快捷键Alt+F7）

![这里写图片描述](http://img.blog.csdn.net/20160921172309557)

结果在find窗口中

![这里写图片描述](http://img.blog.csdn.net/20160921172318369)

ctrl+F7就是该方法在当前类中的被使用到的地方

### 7. ctrl + o 查看所有可以重写的方法。

![这里写图片描述](http://img.blog.csdn.net/20161109100443791)

### 8. 在类中快速定位某个方法或属性Ctrl+F12

![这里写图片描述](http://img.blog.csdn.net/20170223193105820?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvaHVhbmd4aWFvbWluZ2xpcGVuZw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

全局搜索

![1493641715076](img/1493641715076.png)

搜索指令 ctrl + shift + A

![1493641916719](img/1493641916719.png)

查找调用 Ctrl + G

![1493642513190](img/1493642513190.png)

## 断点调试

### 条件断点

断点，右键

![1493642792462](img/1493642792462.png)

### 临时断点

Ctrl + Alt + shift + f8

![1493644425194](img/1493644425194.png)

### 异常断点

![1493643739410](img/1493643739410.png)

![1493643831942](img/1493643831942.png)

### 日志断点

![1493644157059](img/1493644157059.png)

## 附加调试

正常启动程序，点击附加调试按钮，随时进入调试模式

![1493646521249](img/1493646521249.png)

## 代码提示

Alt + /，智能提示 Alt + shift + 空格

## Surround With

Ctrl + Alt + T

![1493646894262](img/1493646894262.png)

## 重构代码

把重复代码抽取成一个方法

![1493648908281](img/1493648908281.png)

![1493649010582](img/1493649010582.png)

抽取xml属性

![1493649339564](img/1493649339564.png)

![1493649378821](img/1493649378821.png)

抽取layout

![1493649467616](img/1493649467616.png)

## template

后缀模板

## 项目模板

## theme editor

![1493653206101](img/1493653206101.png)

## 分析代码

![1493652440486](img/1493652440486.png)

## 方法调用栈

Ctrl + Alt + H

![1493652722894](img/1493652722894.png)

## 版本控制

![1493652874988](img/1493652874988.png)

![1493652929510](img/1493652929510.png)

![1493653686947](img/1493653686947.png)

## Instant Run

![1493653783235](img/1493653783235.png)

![1493653834182](img/1493653834182.png)

## gradle

### aar

![1493656404973](img/1493656404973.png)

## 找打开的页面是哪个Activity

当跳转到一个Activity的时候，logcat会打印一条日志，显示开启的Activity

![1495365715459](img/1495365715459.png)

## 代码回退

代码未commit

![1495419170883](img/1495419170883.png)

代码已commit

![1495419472719](img/1495419472719.png)

![1495419590193](img/1495419590193.png)

## 合并分支

![1495419900205](img/1495419900205.png)

![1495419942338](img/1495419942338.png)