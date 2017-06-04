---
typora-copy-images-to: img
---

## 插件的安装

File → Settings → Plugins

![1493264039167](img/1493264039167.png)

![1493264039167](img/plugin.png)

## 常用插件

下载地址:http://plugins.jetbrains.com/

| 插件                                | 功能描述                      |
| :-------------------------------- | :------------------------ |
| ADB Idea                          | 方便卸载apk,删除缓存              |
| Android ButterKnife Zelezny       | ButterKnife对应的插件          |
| Android Code Generator Plugin     | 生成ViewHolder,生成initView方法 |
| Codota                            | 搜索代码块                     |
| GsonFormat                        | jsonString自动转bean插件       |
| genymotion-idea-plugin            | genymotion对应的插件           |
| SelectorChapek for Android        | 帮助生成selector              |
| Sexy Editor                       | 代码区域加背景                   |
| Android Drawable Importer         | 同一张图片生成多个自动生成多分辨率图片       |
| Android Layout ID Converter       | xml到控件的转换                 |
| Android Postfix Completion        | toast和log加强               |
| Android Studio Prettify           | 帮助findViewById            |
| .ignore                           | git忽略文件高亮效果,文件夹颜色提示       |
| Android Parcelable code generator | 生成Parcelable代码            |
| Gradle Dependencies Helper        | gradle帮助插件                |
| Android Toolbox Plugin            | 生成ViewHolder,意义不大         |

##  GsonFormat

使用快捷键Alt + Insert

![1493265085025](img/1493265085025.png)

![1493265205777](img/1493265205777.png)

把需要格式化的json粘贴进去

```json
{
    "tList": [
        {
            "template": "normal1",
            "topicid": "0001899N",
            "hasCover": false,
            "weburl": "http://www.163.com/",
            "alias": "Top News",
            "subnum": "3.2万",
            "recommendOrder": 0,
            "isNew": 0,
            "hashead": 1,
            "img": "",
            "isHot": 0,
            "hasIcon": false,
            "cid": "C1348646712614",
            "recommend": "0",
            "headLine": true,
            "hasAD": 1,
            "color": "",
            "bannerOrder": 0,
            "tname": "头条",
            "ename": "androidnews",
            "showType": "comment",
            "special": 0,
            "tid": "T1348647909107",
            "ad_type": 1
        },
        {
            "template": "normal1",
            "topicid": "0001899N;000187QQ",
            "hasCover": false,
            "alias": "yaowenspecial",
            "subnum": "10.6万",
            "recommendOrder": 0,
            "isNew": 0,
            "hashead": 1,
            "img": "",
            "isHot": 0,
            "hasIcon": false,
            "cid": "C1348647991705",
            "recommend": "0",
            "headLine": false,
            "hasAD": 1,
            "color": "",
            "bannerOrder": 0,
            "tname": "要闻",
            "ename": "yaowenspecial",
            "showType": "comment",
            "special": 0,
            "tid": "T1467284926140",
            "ad_type": 1
        },
        {
            "template": "recommend",
            "topicid": "00037VVH",
            "hasCover": false,
            "weburl": "http://ent.163.com/",
            "alias": "Entertainment",
            "subnum": "超过1000万",
            "recommendOrder": 120,
            "isNew": 0,
            "hashead": 1,
            "img": "T1348648517839",
            "isHot": 0,
            "hasIcon": true,
            "cid": "C1348648351901",
            "recommend": "1",
            "headLine": false,
            "hasAD": 1,
            "color": "",
            "bannerOrder": 0,
            "tname": "娱乐",
            "ename": "yule",
            "showType": "comment",
            "special": 0,
            "tid": "T1348648517839",
            "ad_type": 1
        }
    ]
}
```

选择需要生成javabean的字段

![1493265297823](img/1493265297823.png)

生成的javabean

```java
public class TList {

    public List<TListEntity> tList;

    public static class TListEntity {
        public String  template;
        public String  topicid;
        public boolean hasCover;
        public String  weburl;
        public String  alias;
        public String  subnum;
        public int     recommendOrder;
        public int     isNew;
        public int     hashead;
        public String  img;
        public int     isHot;
        public boolean hasIcon;
        public String  cid;
        public String  recommend;
        public boolean headLine;
        public int     hasAD;
        public String  color;
        public int     bannerOrder;
        public String  tname;
        public String  ename;
        public String  showType;
        public int     special;
        public String  tid;
        public int     ad_type;
    }
}
```

## Android ButterKnife Zelezny

![](http://upload-images.jianshu.io/upload_images/1187237-feba5f66498116b3.gif?imageMogr2/auto-orient/strip)

## [Android-Studio-Plugins](https://github.com/ydmmocoo/Android-Studio-Plugins)

现在Android的开发者基本上都使用Android Studio进行开发(如果你还在使用eclipse那也行，毕竟你乐意怎么样都行)。使用好Android Studio插件能大量的减少我们的工作量。
# 1.[GsonFormat](http://plugins.jetbrains.com/plugin/7654?pr=androidstudio)
快速将json字符串转换成一个Java Bean，免去我们根据json字符串手写对应Java Bean的过程。

![](http://plugins.jetbrains.com/files/7654/screenshot_15729.png)

使用方法：快捷键Alt+S也可以使用Alt+Insert选择GsonFormat

# 2.[Android ButterKnife Zelezny](http://plugins.jetbrains.com/plugin/7369?pr=androidstudio)
配合ButterKnife实现注解，从此不用写findViewById，想着就爽啊。在Activity，Fragment，Adapter中选中布局xml的资源id自动生成butterknife注解。

![](http://plugins.jetbrains.com/files/7369/screenshot_14384.png)

使用方法：Ctrl+Shift+B选择图上所示选项

# 3.[Android Code Generator](http://plugins.jetbrains.com/plugin/7595?pr=androidstudio)
根据布局文件快速生成对应的Activity，Fragment，Adapter，Menu。

![](http://plugins.jetbrains.com/files/7595/screenshot_14834.png)
![](http://plugins.jetbrains.com/files/7595/screenshot_14833.png)

# 4.[Android Parcelable code generator](http://plugins.jetbrains.com/plugin/7332?pr=androidstudio)
JavaBean序列化，快速实现Parcelable接口。

![](https://segmentfault.com/image?src=http://img.blog.csdn.net/20160416104459926&objectId=1190000005092842&token=ab29ed79d41be9e42b3a3d2ed1ec3bef)

# 5.[Android Methods Count](http://plugins.jetbrains.com/plugin/8076?pr=androidstudio)
显示依赖库中得方法数

![](http://plugins.jetbrains.com/files/8076/screenshot_15509.png)

# 6.[Lifecycle Sorter](http://plugins.jetbrains.com/plugin/7742?pr=androidstudio)
可以根据Activity或者fragment的生命周期对其生命周期方法位置进行先后排序，快捷键Ctrl + alt + K

![](http://plugins.jetbrains.com/files/7742/screenshot_15071.png)
![](http://plugins.jetbrains.com/files/7742/screenshot_15070.png)

# 7.[CodeGlance](http://plugins.jetbrains.com/plugin/7275?pr=androidstudio)
在右边可以预览代码，实现快速定位

![](http://plugins.jetbrains.com/files/7275/screenshot_14294.png)
![](http://plugins.jetbrains.com/files/7275/screenshot_14295.png)

# 8.[findBugs-IDEA](http://plugins.jetbrains.com/plugin/3847?pr=androidstudio)
查找bug的插件，Android Studio也提供了代码审查的功能（Analyze-Inspect Code...）

![](http://plugins.jetbrains.com/oldimg/screenshots/FindBugs-IDEA_2541.png)

# 9.[ADB WIFI](http://plugins.jetbrains.com/plugin/7856?pr=androidstudio)
使用wifi无线调试你的app，无需root权限
也可参考以下文章：
[Android wifi无线调试App新玩法ADB WIFI](http://www.jianshu.com/p/21d1b65d92a4)

![](http://plugins.jetbrains.com/files/7856/screenshot_15153.png)

# 10.[AndroidPixelDimenGenerator](https://github.com/succlz123/AndroidPixelDimenGenerator)
Android Studio自动生成dimen.xml文件插件

![](https://github.com/succlz123/AndroidPixelDimenGenerator/raw/master/snapshot/1.jpeg)

# 11.[JsonOnlineViewer](http://plugins.jetbrains.com/plugin/7838?pr=androidstudio)
在Android Studio中请求、调试接口

![](http://plugins.jetbrains.com/files/7838/screenshot_15113.png)

# 12.[Android Styler](http://plugins.jetbrains.com/plugin/7972?pr=androidstudio)
根据xml自动生成style代码的插件

![](http://plugins.jetbrains.com/files/7972/screenshot_15340.png)
![](http://plugins.jetbrains.com/files/7972/screenshot_15339.png)
![](http://plugins.jetbrains.com/files/7972/screenshot_15338.png)

## Usage:
a. copy lines with future style from your layout.xml file 
b. paste it to styles.xml file with Ctrl+Shift+D (or context menu) 
c. enter name of new style in the modal window
d. your style is prepared! 

# 13.[Android Drawable Importer](http://plugins.jetbrains.com/plugin/7658?pr=androidstudio)
这是一个非常强大的图片导入插件。它导入Android图标与Material图标的Drawable ，批量导入Drawable ，多源导入Drawable（即导入某张图片各种dpi对应的图片）

![](http://plugins.jetbrains.com/files/7658/screenshot_15535.png)
![](http://plugins.jetbrains.com/files/7658/screenshot_15691.png)
![](http://plugins.jetbrains.com/files/7658/screenshot_15533.png)
![](http://plugins.jetbrains.com/files/7658/screenshot_15537.png)
![](http://plugins.jetbrains.com/files/7658/screenshot_15536.png)
![](http://plugins.jetbrains.com/files/7658/screenshot_15534.png)
![](http://plugins.jetbrains.com/files/7658/screenshot_15532.png)
![](http://plugins.jetbrains.com/files/7658/screenshot_15351.png)

# 14.[SelectorChapek for Android](http://plugins.jetbrains.com/plugin/7298?pr=androidstudio)
通过资源文件命名自动生成Selector文件。

![](http://plugins.jetbrains.com/files/7298/screenshot_14292.png)
![](http://plugins.jetbrains.com/files/7298/screenshot_14291.png)
![](http://plugins.jetbrains.com/files/7298/screenshot_14290.png)

# 15.[GenerateSerialVersionUID](http://plugins.jetbrains.com/plugin/185?pr=androidstudio)
实现Serializable序列化bean

Adds a new action 'SerialVersionUID' in the generate menu (alt + ins). The action adds an serialVersionUID field in the current class or updates it if it already exists, and assigns it the same value the standard 'serialver' JDK tool would return. The action is only visible when IDEA is not rebuilding its indexes, the class is serializable and either no serialVersionUID field exists or its value is different from the one the 'serialver' tool would return.

# 16.[genymotion](http://plugins.jetbrains.com/plugin/7269?pr=androidstudio)
速度较快的android模拟器

![](http://plugins.jetbrains.com/files/7269/screenshot_14278.png)

# 17.[LeakCanary](https://github.com/square/leakcanary)
帮助你在开发阶段方便的检测出内存泄露的问题，使用起来更简单方便。
可以参考以下文章：
[LeakCanary 中文使用说明](http://www.liaohuqiu.net/cn/posts/leak-canary-read-me/)

![](http://stormzhang.com/image/leakcaneray.png)

# 18.[Android Postfix Completion](http://plugins.jetbrains.com/plugin/7775?pr=androidstudio)
可根据后缀快速完成代码，这个属于拓展吧，系统已经有这些功能，如sout、notnull等，这个插件在原有的基础上增添了一些新的功能，我更想做的是通过原作者的代码自己定制功能，那就更爽了

![](http://plugins.jetbrains.com/files/7775/screenshot_15042.png)

# 19.[Android Holo Colors Generator](https://plugins.jetbrains.com/plugin/7366?pr=)
通过自定义Holo主题颜色生成对应的Drawable和布局文件

![](https://plugins.jetbrains.com/files/7366/screenshot_14379.png)

# 20.[dagger-intellij-plugin](https://github.com/square/dagger-intellij-plugin)
dagger可视化辅助工具

![](https://github.com/square/dagger-intellij-plugin/raw/master/images/inject-to-provide.gif)

# 21.[GradleDependenciesHelperPlugin](https://github.com/ligi/GradleDependenciesHelperPlugin)
maven gradle 依赖支持自动补全

![](https://camo.githubusercontent.com/d9b1b39eda21e0e33b656e2821f01897d915f7c5/68747470733a2f2f6c68332e676f6f676c6575736572636f6e74656e742e636f6d2f2d51364e7970315864594c772f556a73325a5175666634492f414141414141414144624d2f624d704c516742664d6b632f773538372d683330392d6e6f2f696465615f677261646c655f706c7567696e2e706e67)

# 22.[RemoveButterKnife](https://github.com/u3shadow/RemoveButterKnife)
ButterKnife这个第三方库每次更新之后，绑定view的注解都会改变，从bind,到inject，再到bindview，搞得很多人都不敢升级，一旦升级，就会有巨量的代码需要手动修改，非常痛苦
当我们有一些非常棒的代码需要拿到其他项目使用，但是我们发现，那个项目对第三方库的使用是有限制的，我们不能使用butterknife，这时候，我们又得从注解改回findviewbyid
针对上面的两种情况，如果view比较少还好说，如果有几十个view，那么我们一个个的手动删除注解，写findviewbyid语句，简直是一场噩梦（别问我为什么知道这是噩梦）
所以，这种有规律又重复简单的工作为什么不能用一个插件来实现呢？于是RemoveButterKnife的想法就出现了。

[具体介绍](http://www.u3coding.com/2016/06/24/androidstudio-plugin-removebutterknife-di/)

![](https://camo.githubusercontent.com/0327cda5b531ab6f2b803abe295c42225668d28d/687474703a2f2f7777772e7533636f64696e672e636f6d2f77702d636f6e74656e742f75706c6f6164732f323031362f30362f312e676966)

# 23.[AndroidProguardPlugin](https://github.com/zhonghanwen/AndroidProguardPlugin)
一键生成项目混淆代码插件，值得你安装~(不过目前可能有些第三方项目的混淆还未添加完全)

![](http://7xrnko.com1.z0.glb.clouddn.com/androidproguard1.gif)

# 24.[otto-intellij-plugin](https://github.com/square/otto-intellij-plugin)
otto事件导航工具。

![](https://github.com/square/otto-intellij-plugin/raw/master/images/produce-to-subscribe.gif)
![](https://github.com/square/otto-intellij-plugin/raw/master/images/event-to-subscribe.gif)

# 25.[eventbus-intellij-plugin](https://github.com/kgmyshin/eventbus-intellij-plugin)
eventbus导航插件(对于最新版的 EventBus 3.0.0 好像无效,请替换为eventbus3-intellij-plugin此插件地址在本文第51个)

![](https://raw.githubusercontent.com/kgmyshin/eventbus-intellij-plugin/master/art/cap.gif)

# 26.[idea-markdown](https://github.com/nicoulaj/idea-markdown)
markdown插件

![](https://github.com/nicoulaj/idea-markdown/raw/assets/screenshots/preview.png)

# 27.[Sexy Editor](https://plugins.jetbrains.com/plugin/1833?pr=androidstudio)
设置AS代码编辑区的背景图

首先点击界面的设置按钮 进入设置界面，选中Plugins,右边选择 Browser ... ，输入Sexy ... 下面自动弹出候选插件，右边点击Install 安装
![](http://d.hiphotos.baidu.com/zhidao/wh%3D600%2C800/sign=f57bdd37f0246b607b5bba72dbc83674/4b90f603738da9777260054fb651f8198618e303.jpg)
安装成功 后需要重启AS
![](http://h.hiphotos.baidu.com/zhidao/wh%3D600%2C800/sign=77e4e517fdf2b211e47b8d48fab04900/1c950a7b02087bf46d0dd48df4d3572c10dfcff5.jpg)
重启完成之后 进入设置界面 选择other Setting 下的Sexy Editor ， 右侧 insert 一张或多张图片即可，上面的其他设置可以设置方位 间隔时间 透明度等等，设置完成后，要关闭打开的文件，重新打开项目文件即可在代码编辑区显示插入的图片，作为代码编辑区的背景图。
![](http://h.hiphotos.baidu.com/zhidao/wh%3D600%2C800/sign=5cd9b28564d9f2d320442ce999dca62b/34fae6cd7b899e51289eb77044a7d933c8950d45.jpg)

# 28.[folding-plugin](https://github.com/dmytrodanylyk/folding-plugin)
布局文件分组的插件

![](https://github.com/dmytrodanylyk/folding-plugin/raw/master/screenshots/Preview.png)

# 29.[Android-DPI-Calculator](https://github.com/JerzyPuchalski/Android-DPI-Calculator)
DPI计算插件

![](https://camo.githubusercontent.com/ce3be2aaa3b1f70b90f5b825c529694509d70313/68747470733a2f2f7261772e6769746875622e636f6d2f4a65727a7950756368616c736b692f416e64726f69642d4450492d43616c63756c61746f722f6d61737465722f696d672f6469616c6f672e706e67)

使用：
![](https://camo.githubusercontent.com/598d3b5c9efc5f0b57b58c25a79a323d06307fad/68747470733a2f2f7261772e6769746875622e636f6d2f4a65727a7950756368616c736b692f416e64726f69642d4450492d43616c63756c61746f722f6d61737465722f696d672f616374696f6e2e706e67)
或者
![](https://camo.githubusercontent.com/7a8f977de7a1ba6cd23fb64cbd37566690c27cdc/68747470733a2f2f7261772e6769746875622e636f6d2f4a65727a7950756368616c736b692f416e64726f69642d4450492d43616c63756c61746f722f6d61737465722f696d672f6d656e752e706e67)

# 30.[gradle-retrolambda](https://github.com/evant/gradle-retrolambda)
在java 6 7中使用 lambda表达式插件

修改编译的jdk为java8:
![](http://img.blog.csdn.net/20160311101644127)

# 31.[Android Studio Prettify](https://plugins.jetbrains.com/plugin/7405)
可以将代码中的字符串写在string.xml文件中

选中字符串鼠标右键选择图中所示
![](https://plugins.jetbrains.com/files/7405/screenshot_14417.png)

这个插件还可以自动书写findViewById
![](https://plugins.jetbrains.com/files/7405/screenshot_14418.png)

![](https://plugins.jetbrains.com/files/7405/screenshot_14416.png)

![](https://plugins.jetbrains.com/files/7405/screenshot_14501.png)

![](https://plugins.jetbrains.com/files/7405/screenshot_14419.png)

![](https://plugins.jetbrains.com/files/7405/screenshot_14415.png)

# 32.[Material Theme UI](https://plugins.jetbrains.com/plugin/8006?pr=)
添加Material主题到你的AS

![](https://plugins.jetbrains.com/files/8006/screenshot_15722.png)

![](https://plugins.jetbrains.com/files/8006/screenshot_15723.png)

![](https://plugins.jetbrains.com/files/8006/screenshot_15721.png)

# 33.[.ignore](https://plugins.jetbrains.com/plugin/7495?pr=)
我们都知道在Git 中想要过滤掉一些不想提交的文件，可以把相应的文件添加到.gitignore 中，而.gitignore 这个Android Studio 插件根据不同的语言来选择模板，就不用自己在费事添加一些文件了，而且还有自动补全功能，过滤文件再也不要复制文件名了。我们做项目的时候，并不是所有文件都是要提交的，比如构建的build 文件夹，本地配置文件，每个Module 生成的iml 文件，但是我们每次add，commit 都会不小心把它们添加上去，而gitignore 就是解决这种痛点的，如果你不想提交的文件，就可以在创建项目的时候将这个文件中添加即可，将一些通用的东西屏蔽掉。

![](https://plugins.jetbrains.com/files/7495/screenshot_14960.png)

![](https://plugins.jetbrains.com/files/7495/screenshot_14958.png)

![](https://plugins.jetbrains.com/files/7495/screenshot_14959.png)

# 34.[CheckStyle-IDEA](https://plugins.jetbrains.com/plugin/1065?pr=)
CheckStyle-IDEA 是一个检查代码风格的插件，比如像命名约定，Javadoc，类设计等方面进行代码规范和风格的检查，你们可以遵从像Google Oracle 的Java 代码指南 ，当然也可以按照自己的规则来设置配置文件，从而有效约束你自己更好地遵循代码编写规范。

# 35.[Markdown Navigator](https://plugins.jetbrains.com/plugin/7896?pr=)
github:[Markdown Navigator](https://github.com/vsch/idea-multimarkdown/wiki)
Markdown插件

![](https://plugins.jetbrains.com/files/7896/screenshot_15818.png)

# 36.[ECTranslation](https://github.com/Skykai521/ECTranslation)
Android Studio Plugin,Translate English to Chinese. Android Studio 翻译插件,可以将英文翻译为中文。

![](https://github.com/Skykai521/ECTranslation/raw/master/img/translation_img.png)

# 37.[PermissionsDispatcher plugin](https://plugins.jetbrains.com/plugin/8349)
github:[PermissionsDispatcher plugin](https://github.com/shiraji/permissions-dispatcher-plugin)
自动生成6.0权限的代码

![](https://github.com/shiraji/permissions-dispatcher-plugin/raw/master/website/images/pd.gif)

# 38.[WakaTime](https://plugins.jetbrains.com/plugin/7425?pr=)
github:[WakaTime](https://github.com/wakatime/jetbrains-wakatime)
记录你在IDE上的工作时间

![](https://plugins.jetbrains.com/files/7425/screenshot_14794.png)

# 39.[AndroidWiFiADB](https://github.com/pedrovgs/AndroidWiFiADB)
无线调试应用

![](https://github.com/pedrovgs/AndroidWiFiADB/raw/master/art/screenshot1.gif)

![](https://github.com/pedrovgs/AndroidWiFiADB/raw/master/art/android_devices_window.png)

# 40.[AndroidLocalizationer](https://github.com/westlinkin/AndroidLocalizationer)
可用于将项目中的 string 资源自动翻译为其他语言的 Android Studio/IntelliJ IDEA 插件

![](https://raw.githubusercontent.com/westlinkin/AndroidLocalizationer/master/screen_shot_3.png)

![](https://raw.githubusercontent.com/westlinkin/AndroidLocalizationer/master/screen_shot_2.png)

# 41.[TranslationPlugin](https://github.com/YiiGuxing/TranslationPlugin)
又一翻译插件,可中英互译。

![](https://raw.githubusercontent.com/YiiGuxing/TranslationPlugin/master/images/1.png)

![](https://raw.githubusercontent.com/YiiGuxing/TranslationPlugin/master/images/3.png)

# 42.[SingletonTest](https://github.com/luhaoaimama1/SingletonTest)
快速生成单例模式的预设

![](https://github.com/luhaoaimama1/SingletonTest/raw/master/demo/tip1.png)

![](https://github.com/luhaoaimama1/SingletonTest/raw/master/demo/tip2.png)

![](https://github.com/luhaoaimama1/SingletonTest/raw/master/demo/tip3.png)

# 43.[BorePlugin](https://github.com/boredream/BorePlugin)
Android Studio 自动生成布局代码插件

![](https://github.com/boredream/BorePlugin/raw/master/screenshot/LayoutCreator.gif)

## 代码生成规则

a.自动遍历目标布局中所有带id的文件, 无id的不会识别处理
b.控件生成的变量名默认为id名称, 可以在弹出确认框右侧的名称输入栏中自行修改
c.所有的Button或者带clickable=true的控件, 都会自动在代码中生成setOnClickListener相关代码
d.所有EditText控件, 都会在代码中生成非空判断代码, 如果为空会提示EditText的hint内容, 如果hint为空则提示xxx字符串不能为空字样, 最后会把所有输入框的验证合并到一个submit方法中
e.会自动识别布局中的include标签, 并读取对应布局中的控件

# 44.[jimu Mirror](http://www.jimumirror.com/mirror-downloads/)
能够实时预览Android布局，它会监听布局文件的改动，如果有代码变化，就会立即刷新UI。

# 45.[jRebel For Android](http://zeroturnaround.com/software/jrebel-for-android/)
不仅能够做到UI布局的实时预览，它甚至做到了让你更改java代码后就能实时替换apk中的类文件，达到应用实时刷新，官网的介绍是：Skip build, install and run，因此它可以节约我们很多很多的时间，它的效果也十分不错。

![](http://zeroturnaround.com/wp-content/uploads/2015/04/Android_Card1_2x.png)

![](http://zeroturnaround.com/wp-content/uploads/2015/04/Android_Card2_2x.png)

![](http://zeroturnaround.com/wp-content/uploads/2015/04/Android_Card3_2x.png)

# 46.[sdk-manager-plugin](https://github.com/JakeWharton/sdk-manager-plugin)
SDK管理插件，自动检测更新并下载。(图片与插件无关哈)

![](https://camo.githubusercontent.com/95469d65798f62a50a9fcabe21e2cc303a1b859c/687474703a2f2f692e696d6775722e636f6d2f384a734a587a6e2e6a7067)

# 47.[Codota](http://www.codota.com/)
搜索最好的Android代码。(Studio里面直接可以搜到此插件)

# 48.[LayoutFormatter](https://github.com/drakeet/LayoutFormatter)
drakeet 开发一个一键格式化你的 XML 文件的 Android Studio 插件，至于为什么不用 Android Studio 自带的格式化功能而用这个插件，可以看下作者的一篇 Blog -> [当我们谈 XML 布局文件代码的优雅性](https://drakeet.me/layoutformatter)

![](http://ww1.sinaimg.cn/large/86e2ff85gw1f383wa95tej21ge0m5ai0.jpg)

# 49.[android-strings-search-plugin](https://github.com/konifar/android-strings-search-plugin)
一个可以通过输入文字找到strings.xml资源的插件

![](https://github.com/konifar/android-strings-search-plugin/raw/master/art/demo.gif)

# 50.[ideaVim](http://plugins.jetbrains.com/plugin/164?pr=androidstudio)
vim 本身就是一款很优秀的文本编辑器，而Android Studio 更是一款编写APP应用的神器。如果两个款优秀的软件结合在一起感觉会怎样呢？
详细请看文章:[Android Studio ＋Vim](http://www.jianshu.com/p/43862126b88f)

![](http://upload-images.jianshu.io/upload_images/1825722-8b55d9654777599e.gif?imageMogr2/auto-orient/strip)

# 51.[eventbus3-intellij-plugin](https://github.com/likfe/eventbus3-intellij-plugin/blob/master/README-zh.md)
引导 EventBus 的 post 和 event(对于最新版的 EventBus 3.0.0 有效)
主要Bug修复工作：
修改包名和方法名以适应 EventBus 3.X
替换一个在新版的 intellij plugin SDK 已经不存在的类
增加若干 try-catch ，防止插件崩溃

![](https://raw.githubusercontent.com/likfe/eventbus3-intellij-plugin/master/art/cap.gif)

# 52.[Exynap](http://exynap.com/)
Exynap 一个帮助开发者自动生成样板代码的 AndroidStudio 插件

![](http://exynap.com/images/anim01.gif)

# 53.[gradle-cleaner-intellij-plugin](https://github.com/Softwee/gradle-cleaner-intellij-plugin)
Force clear delaying & no longer needed Gradle tasks.

![](https://camo.githubusercontent.com/cb48bca7f8bd0b513f350f7320c74054d1b9fbce/687474703a2f2f6936352e74696e797069632e636f6d2f726a687863382e706e67)

# 54.[MVPHelper](http://androidwing.net/index.php/27)
一款Intellj IDEA 和Android Studio的插件，可以为MVP生成接口以及实现类，解放双手。
具体请查看[Android Studio插件之MVPHelper，一键生成MVP代码](http://androidwing.net/index.php/27)一文

![](https://github.com/githubwing/MVPHelper/raw/master/img/mvp_presenter.gif)

