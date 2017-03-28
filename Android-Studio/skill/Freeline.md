我们知道 [Android](http://lib.csdn.net/base/android) 的编译很慢，尤其是项目大点的时候，那编译速度简直难以忍受，极大的降低了我们的开发效率，之前的文章「[Android 高效调试神器 JRebel](http://blog.csdn.net/googdev/article/details/53470931)」给大家介绍过，但是是付费的，用起来不是那么自由，而今天给大家介绍另外一个强大的工具 – [Freeline](https://github.com/alibaba/freeline)，绝对秒级编译。

## 什么是 Freeline？

[Freeline](https://github.com/alibaba/freeline) 是蚂蚁金服旗下平台蚂蚁聚宝 Android 团队开发的一款针对 Android 平台的增量编译工具，它可以充分利用缓存文件，在几秒钟内迅速地对代码的改动进行编译并部署到设备上，有效地减少了日常开发中的大量重新编译与安装的耗时，现已开源。

稳定性方面：完善的基线对齐，进程级别异常隔离机制。

性能方面：内部采用了类似 Facebook 的开源工具 buck 的多工程多任务并发思想：端口扫描，代码扫描，并发编译，并发 dx，并发 merge dex 等策略，在多核机器上有明显加速效果，另外在 class 及 dex,resources 层面作了相应缓存策略，做到真正增量开发，另外引入并优化 buck 的部分加速组件 dx，DexMerger，资源编译方面，深入改造了 Aapt 资源编译流程，当资源发生改变时候，秒级完成增量包编译，其中增量包仅含最小的变更集合（10Kb～数百Kb内），后期也被运用到线上进行资源/代码动态替换。相比目前 instant-run，buck，layoutcast 等方案快数倍速度。

## 有何优势？

1. 真增量，构建过程快且增量包体积小，极大提升更改代码部署到手机速度，较 Android studio 2.0 及 LayoutCast 快 3～5 倍
2. 跨平台 [Linux](http://lib.csdn.net/base/linux)，mac，windows
3. 全版本覆盖 2.x ～ 6.x版本均支持
4. 部署流程简化，更改代码后，构建过程中，与手机建立了 tcp 长连接，一行命令即可完成增量部署，毋需到各自子 bundle 所在的目录构建完成后再进入 portal/launcher 进行打包再安装到手机的过程
5. 事务支持，在开发过程引入的异常不会破坏工作空间
6. 无缝支持 mPass,解决了类似 maven 各个节点需 merge 合并等与常规开发流程不一致的问题
7. 进程级别异常隔离，开发体验持续稳定

## 支持的功能

- 支持标准的多模块Gradle工程的增量构建
- 并发执行增量编译任务
- 进程级别异常隔离机制
- 支持so动态更新
- 支持resource.arsc缓存
- 支持retrolambda
- 支持DataBinding
- 支持各类主流注解库
- 支持Windows，Linux，Mac平台

## 如何使用？

首先你的电脑上应该安装 [Python](http://lib.csdn.net/base/python)，如果没有安装，请自行搜索安装，相信你可以搞得定。

其次配置 project-level 的 build.gradle，加入 freeline-gradle 的依赖：

```
buildscript {
    repositories {
        jcenter()
    }
    dependencies {
        classpath 'com.antfortune.freeline:gradle:0.8.2'
    }
}1234567812345678
```

然后，在你的主 module 的 build.gradle 中，一般也就是你 app 目录下的 build.gradle 文件，应用 freeline 插件的依赖，记得点击 **Sync** 按钮进行同步下载。

```
apply plugin: 'com.antfortune.freeline'

android {
    ...
}1234512345
```

最后，在命令行执行以下命令来下载 freeline 的 python 和二进制依赖，注意切换到项目目录执行：

- Windows[CMD]: **gradlew initFreeline**
- Linux/Mac: **./gradlew initFreeline**

对于国内的用户来说，如果你的下载的时候速度很慢，你也可以加上参数，执行gradlew initFreeline -Pmirror，这样就会从国内镜像地址来下载。

下载完成之后，在命令行输入 **python freeline.py** 即可进行编译运行。

当然如果每次都输入也挺麻烦的，最简单的用法是直接安装 Android Studio 插件。

在 Android Studio 中，通过以下路径 Preferences → Plugins → Browse repositories，搜索“freeline”，并安装，之后你会看到工具栏有如下按钮：

![img](http://stormzhang.com/image/freeline.jpeg)

直接点击 Run Freeline 的按钮，本质上也就是帮你在命令行输入上述命令而已。

## 使用体验

自己在项目上亲自体验了，综合使用下来确实很爽，真正实现了秒级编译，不管你是更改了代码文件还是资源文件，直接编译运行真正是秒级的，而在之前可能得等上个一两分钟。但是使用下来有以下注意事项：

- 第一次增量资源编译的时候有点慢，不过也就在第一次的时候慢，后面速度蹭蹭的；
- 如果设备上之前有安装不是用 Freeline 编译打包的 apk，请先卸载，之后再用 Freeline 编译打包；
- 第一次 Freeline 编译安装之后不会自动启动 App，这点请大家注意下，因为第一次我一直在等待，等了好久以为没成功，后来才发现其实安装成功了的，只是没有打开而已；
- 不支持多设备同时连接，也就是说不管是模拟器还是真机，只允许同时一台设备连接，否则会失败；
- 不支持删除带 id 的资源，否则可能导致 aapt 编译出错；
- 如果你的项目有使用 Kotlin 语言，那么 Freeline 不支持；
- 如果你的项目又想用 Freeline，又想使用 Gradle，记得执行 Gradle 脚本之前先执行 **./gradlew clean**，否则会编译失败；

总体而已 Freeline 会有一些限制，以及兼容性可能也会有点问题，但是试用下来没遇到多大的问题，而且对于调试的效率提升简直太大了，值得推荐给大家！

------

PS: 想要更多的了解其原理，请参考以下官方详细介绍。

[https://github.com/alibaba/freeline/blob/master/README-zh.md](https://github.com/alibaba/freeline/blob/master/README-zh.md)

[https://yq.aliyun.com/articles/59122](https://yq.aliyun.com/articles/59122)

> 本文原创发布于[微信](http://lib.csdn.net/base/wechat)公众号 AndroidDeveloper，id：googdev，欢迎关注获取更多优质内容。