各大站长平时除了写博客外，可以使用 gitbook 将一系列的博客专栏整理成电子书出版。这样既方便各大网友阅读，还可以带来新的离线阅读功能。

在以前我们只能靠出版社，或者编写 word 文档，来实现。然而有了 gitbook 之后，一切都变得那么简单了。今天就为大家分享一下，如果在 Windows 系统上安装 gitbook，进行电子书的编写和发布。

# [1. GitBook Editor](https://www.gitbook.com/editor)
最简单的方式就是使用GitBook编辑器，没有什么难度，后面的教程主要针对命令行的方式。

![](https://www.gitbook.com/assets/images/editor/preview_windows.png)

PS：GitBook的book页面默认没有download按钮的

![GitBook](http://upload-images.jianshu.io/upload_images/3981391-8d0c8b6063488ef7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

需要到设置中打开，打开后再次publish生效

![GitBook](http://upload-images.jianshu.io/upload_images/3981391-14e549f7801c794c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 1.1 同步GitHub
![gitbook](http://upload-images.jianshu.io/upload_images/3981391-41675f06ba92da6c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 1.2 更新失败，无法转换成pdf/mobi/epub格式


![gitbook](http://upload-images.jianshu.io/upload_images/3981391-e895f74985d2b8b9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![gitbook](http://upload-images.jianshu.io/upload_images/3981391-7472f7955ba3bb2a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 1.3 Token
```
git config --global gitbook.user username
git config --global gitbook.token yourtoken
```
![token](http://upload-images.jianshu.io/upload_images/3981391-5cbfae01a0d89658.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 2. 安装 nodejs

首先我们需要做的是安装 [Nodejs](http://nodejs.cn/)。大家可以到 [Nodejs](http://nodejs.cn/) 的官网进行下载。下载完成后，执行双击进行运行安装。安装完成后，打开 cmd 命令行，输入 node -v 查看安装的 nodejs 的相关版本信息。

也可以在安装目录中找到 node.exe 文件，打开输入 node -v 查看安装的 nodejs 的相关版本信息。

# 3. nodejs 镜像配置

nodejs 安装完成后，我们就可以开始安装 gitbook 了。但是在安装之前，我们还需要配置一下 nodejs 插件安装的下载镜像地址。因为默认的镜像地址是在国外，需要翻墙才可以访问，因此我们需要设置国内的镜像地址。国内的我推荐大家使用阿里巴巴的镜像地址 http://registry.npm.taobao.org 。执行下面的命令，进行配置。

```
npm config set registry http://registry.npm.taobao.org
```

除了上面的方法外，我们也可以在用户主目录下编辑 .npmrc 文件，添加一行 registry=http://registry.npm.taobao.org 保存就可以了。用户的主目录一般在 C:\Users\Administrator ，具体随你的操作系统系统盘而定。

npm使用介绍：http://www.runoob.com/nodejs/nodejs-npm.html

# 4. 全局安装 gitbook

现在我们可以开始安装全局的 gitbook 了。执行 npm install gitbook-cli -g 命令，进行安装。安装的过程中，由于需要下载安装包，因此大家需要等待一定的时间，具体时长取决于你的网速和硬件配置。

安装完成后，我们可以执行 gitbook -v 查看安装的版本信息。

# 5. gitbook 常用的命令

安装完成了后，我们就可以开始编写内容，进行电子书发布了。具体的操作，大家可以参考《[GitBook简明教程](http://www.chengweiyang.cn/gitbook/installation/README.html)》进行学习。我这里给大家推荐3种最常用的命令

```
gitbook init //初始化目录文件
gitbook help //列出gitbook所有的命令
gitbook --help //输出gitbook-cli的帮助信息
gitbook build //生成静态网页
gitbook serve //生成静态网页并运行服务器
gitbook build --gitbook=2.0.1 //生成时指定gitbook的版本, 本地没有会先下载
gitbook ls //列出本地所有的gitbook版本
gitbook ls-remote //列出远程可用的gitbook版本
gitbook fetch 标签/版本号 //安装对应的gitbook版本
gitbook update //更新到gitbook的最新版本
gitbook uninstall 2.0.1 //卸载对应的gitbook版本
gitbook build --log=debug //指定log的级别
gitbook builid --debug //输出错误信息
```

## gitbook

```
C:\Users\AllenIverson\Desktop\gitcourse>gitbook
 Usage: gitbook [options] [command]


 Commands:

   ls                        List versions installed locally
   current                   Display currently activated version
   ls-remote                 List remote versions available for install
   fetch [version]           Download and install a <version>
   alias [folder] [version]  Set an alias named <version> pointing to <folder>
   uninstall [version]       Uninstall a version
   update [tag]              Update to the latest version of GitBook
   help                      List commands for GitBook
   *                         run a command with a specific gitbook version

 Options:

   -h, --help               output usage information
   -v, --gitbook [version]  specify GitBook version to use
   -d, --debug              enable verbose error
   -V, --version            Display running versions of gitbook and gitbook-cli
```

## gitbook serve

```
C:\Users\AllenIverson\Desktop\gitbook-test>gitbook serve
Live reload server started on port: 35729
Press CTRL+C to quit ...

info: 7 plugins are installed
info: loading plugin "livereload"... OK
info: loading plugin "highlight"... OK
info: loading plugin "search"... OK
info: loading plugin "lunr"... OK
info: loading plugin "sharing"... OK
info: loading plugin "fontsettings"... OK
info: loading plugin "theme-default"... OK
info: found 3 pages
info: found 0 asset files
info: >> generation finished with success in 1.9s !

Starting server ...
Serving book on http://localhost:4000
```

## gitbook ls

```
C:\Users\AllenIverson\Desktop\gitcourse>gitbook ls
GitBook Versions Installed:

    * 3.2.2

Run "gitbook update" to update to the latest version.
```

## gitbook ls-remote

```
C:\Users\AllenIverson\Desktop\gitcourse>gitbook ls-remote
Available GitBook Versions:

     4.0.0-alpha.5, 4.0.0-alpha.4, 4.0.0-alpha.3, 4.0.0-alpha.2, 4.0.0-alpha.1, 3.2.2, 3.2.1, 3.2.0, 3.2.0-pre.1, 3.2.0-
pre.0, 3.1.1, 3.1.0, 3.0.3, 3.0.2, 3.0.1, 3.0.0, 3.0.0-pre.15, 3.0.0-pre.14, 3.0.0-pre.13, 3.0.0-pre.12, 3.0.0-pre.11, 3
.0.0-pre.10, 3.0.0-pre.9, 3.0.0-pre.8, 3.0.0-pre.7, 3.0.0-pre.6, 3.0.0-pre.5, 3.0.0-pre.4, 3.0.0-pre.3, 3.0.0-pre.2, 3.0
.0-pre.1, 2.6.7, 2.6.6, 2.6.5, 2.6.4, 2.6.3, 2.6.2, 2.6.1, 2.6.0, 2.5.2, 2.5.1, 2.5.0, 2.5.0-beta.7, 2.5.0-beta.6, 2.5.0
-beta.5, 2.5.0-beta.4, 2.5.0-beta.3, 2.5.0-beta.2, 2.5.0-beta.1, 2.4.3, 2.4.2, 2.4.1, 2.4.0, 2.3.3, 2.3.2, 2.3.1, 2.3.0,
 2.2.0, 2.1.0, 2.0.4, 2.0.3, 2.0.2, 2.0.1, 2.0.0, 2.0.0-beta.5, 2.0.0-beta.4, 2.0.0-beta.3, 2.0.0-beta.2, 2.0.0-beta.1,
2.0.0-alpha.9, 2.0.0-alpha.8, 2.0.0-alpha.7, 2.0.0-alpha.6, 2.0.0-alpha.5, 2.0.0-alpha.4, 2.0.0-alpha.3, 2.0.0-alpha.2,
2.0.0-alpha.1

Tags:

     latest : 3.2.2
     pre : 4.0.0-alpha.5
```

## gitbook -V

```
C:\Users\AllenIverson\Desktop\gitcourse>gitbook -V
CLI version: 2.3.0
GitBook version: 3.2.2
```

## gitbook pdf

![gitbook pdf](http://upload-images.jianshu.io/upload_images/3981391-7d5e93fba468f90b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

```
C:\Users\AllenIverson\Desktop\gitcourse>gitbook pdf
info: 7 plugins are installed
info: 6 explicitly listed
info: loading plugin "highlight"... OK
info: loading plugin "search"... OK
info: loading plugin "lunr"... OK
info: loading plugin "sharing"... OK
info: loading plugin "fontsettings"... OK
info: loading plugin "theme-default"... OK
info: found 3 pages
info: found 0 asset files

EbookError: Error during ebook generation: 'ebook-convert' is not recognized as an internal or external command,
operable program or batch file.
```
错误提示：ebook-convert不是内部或外部命令，原因是GitBook在生成PDF的过程中使用到calibre的转换功能，没有安装calibre或安装了calibre没有配置环境变量都会导致转换PDF失败
```
C:\Users\AllenIverson\Desktop\gitcourse>gitbook pdf
info: 7 plugins are installed
info: 6 explicitly listed
info: loading plugin "highlight"... OK
info: loading plugin "search"... OK
info: loading plugin "lunr"... OK
info: loading plugin "sharing"... OK
info: loading plugin "fontsettings"... OK
info: loading plugin "theme-default"... OK
info: found 3 pages
info: found 2 asset files
info: >> generation finished with success in 8.6s !
info: >> 1 file(s) generated
```
安装calibre后，转换成功。PS：安装calibre后需要重新启动命令行窗口
## 设置PDF输出格式

book.json
```json
{
  "gitbook": "2.x.x",
  "title": "Go语言圣经",
  "description": "<The Go Programming Language>中文版",
  "language": "zh",
  "structure": {
    "readme": "preface.md"
  },
  "pluginsConfig": {
    "fontSettings": {
      "theme": "white",
      "family": "msyh",
      "size": 2
    },
    "plugins": [
      "yahei",
      "katex",
      "-search"
    ]
  },
  "fontState": {
    "size": "2",
    "family": "sans",
    "theme": "night"
  },
  "pdf": {
    "pageNumbers": true, 
    "fontFamily": "Arial",
    "fontSize": 12,
    "paperSize": "a4",
    "margin": {
      "right": 62,
      "left": 62,
      "top": 56,
      "bottom": 56
    }
  }
}
```
| Variable            | Description                              |
| :------------------ | :--------------------------------------- |
| `pdf.pageNumbers`   | 是否添加页码，默认是true                           |
| `pdf.fontSize`      | 字体大小，默认是12                               |
| `pdf.fontFamily`    | 字体，默认字体是Arial                            |
| `pdf.paperSize`     | Paper size, options are `'a0', 'a1', 'a2', 'a3', 'a4', 'a5', 'a6', 'b0', 'b1', 'b2', 'b3', 'b4', 'b5', 'b6', 'legal', 'letter'` (default is `a4`) |
| `pdf.margin.top`    | Top margin (default is `56`)             |
| `pdf.margin.bottom` | Bottom margin (default is `56`)          |
| `pdf.margin.right`  | Right margin (default is `62`)           |
| `pdf.margin.left`   | Left margin (default is `62`)            |

## gitbook mobi

```
C:\Users\AllenIverson\Desktop\gitcourse>gitbook mobi
info: 7 plugins are installed
info: 6 explicitly listed
info: loading plugin "highlight"... OK
info: loading plugin "search"... OK
info: loading plugin "lunr"... OK
info: loading plugin "sharing"... OK
info: loading plugin "fontsettings"... OK
info: loading plugin "theme-default"... OK
info: found 32 pages
info: found 34 asset files
info: >> generation finished with success in 26.0s !
info: >> 1 file(s) generated
```

## gitbook epub

```
C:\Users\AllenIverson\Desktop\gitcourse>gitbook epub
info: 7 plugins are installed
info: 6 explicitly listed
info: loading plugin "highlight"... OK
info: loading plugin "search"... OK
info: loading plugin "lunr"... OK
info: loading plugin "sharing"... OK
info: loading plugin "fontsettings"... OK
info: loading plugin "theme-default"... OK
info: found 32 pages
info: found 34 asset files
info: >> generation finished with success in 18.5s !
info: >> 1 file(s) generated
```

# 6. calibre

[下载地址](http://calibre-ebook.com/download)

![calibre](http://upload-images.jianshu.io/upload_images/3981391-dc1685249c334339.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## ebook-convert

```
C:\Users\AllenIverson\Desktop\gitcourse>ebook-convert
用法: ebook-convert.exe input_file output_file [options]

转换不同格式的电子书。

input_file 表示输入文件，output_file 表示输出文件。这两者作为命令行参数必须指定到最前面。

输出的电子书格式可由 output_file 的扩展名得到。同时 output_file 也可以是一种以 .EXT 为扩展名的特殊格式。在这种情况下，输出文件的名称则使用输入文件的名称。注意：文件名不能以连字号作为开头。如果 output_
file 不含扩展名，那么它将被视为一个目录并将会在该目录下生成 HTML 格式的“开放式电子书(OEB)”。这些文件会被视为正常文件而被输出插件所识别。

在指定输入和输出文件后，您可以自定义特定的转换选项。根据输入和输出文件的类型不同可用的转换选项也不同。如需获取针对输入和输出文件的帮助，请在命令行中输入 -h。

对于转换系统的完整文档请查阅
https://manual.calibre-ebook.com/conversion.html

给 ebook-convert.exe 传有空格的参数时，请将参数包括在引号中。例如 "C:\some path with spaces"

选项:
  --version       显示程序版本号并退出

  -h, --help      显示此帮助信息并退出

  --list-recipes  列出内建的订阅清单名。您可以通过如下命令创建基于内建订阅清单的电子书： ebook-convert "Recipe
                  Name.recipe" output.epub
```

## ebook-convert --version

```
C:\Users\AllenIverson\Desktop\gitcourse>ebook-convert --version
ebook-convert.exe (calibre 2.81.0)
Created by: Kovid Goyal <kovid@kovidgoyal.net>
```
## 使用
![calibre](http://upload-images.jianshu.io/upload_images/3981391-200aa47662a10f16.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![calibre](http://upload-images.jianshu.io/upload_images/3981391-d55f8ff166ebfabe.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![calibre](http://upload-images.jianshu.io/upload_images/3981391-68ef58754fe4feea.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 7. GitBook 编译，生成pdf报错
最近在使用 GitBook 生成静态网页和pdf文件时，百度，谷歌了很久也没有类似的解决方案，最近发现是版本问题，我把我的相关经验分享给大家！

在执行 gitbook build ，gitbook serve，gitbook pdf等命令均保持。报错了错误提示内容如下：

```
info: 10 plugins are installed
info: 9 explicitly listed
info: loading plugin "baidu"... OK
info: loading plugin "donate"... OK
info: loading plugin "sitemap"... OK
info: loading plugin "highlight"... OK
info: loading plugin "search"... OK
info: loading plugin "lunr"... OK
info: loading plugin "sharing"... OK
info: loading plugin "fontsettings"... OK
info: loading plugin "theme-default"... OK
info: found 24 pages
info: found 2 asset files
warn: "options" property is deprecated, use config.get(key) instead
warn: "options.generator" property is deprecated, use "output.name" instead
error: error while generating page "README.md":

TypeError: this.contentPath is not a function
```

当然也有些网友的报错内容如下：

```
warn: "options" property is deprecated, use config.get(key) instead
warn: "page.progress" property is deprecated
warn: "sections" property is deprecated, use page.content instead
TypeError: Path must be a string. Received undefined
```

这种问题的原因是，gitbook的版本太低。大家执行 gitbook update 命令进行升级，升级到3.2.2版本即可。

也有网友反映，报一下的错：

```
Error: Couldn't locate plugins "baidu, donate", Run 'gitbook install' to install plugins from registry.
```

这是提示插件没有安装的错误。大家执行 gitbook install 命令完成安装即可。

![gitbook install](http://upload-images.jianshu.io/upload_images/3981391-0e12415cc8846989.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 8. [gitbook-convert](https://github.com/GitbookIO/gitbook-convert)
把docx、xml、html、odt文档转成GitBook

## 安装
```
$ npm install gitbook-convert -g
```
## 常用命令

![gitbook-convert](http://upload-images.jianshu.io/upload_images/3981391-24614430f8fc2ac1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 使用
```
$ gitbook-convert [options] <file> [export-directory]
```

![gitbook-convert](http://upload-images.jianshu.io/upload_images/3981391-4a49aed0f136dbe3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![gitbook-convert](http://upload-images.jianshu.io/upload_images/3981391-8d69bf8557ebe4d3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 9. 常用插件

Gitbook 本身功能丰富，但同时可以使用插件来进行个性化定制。[Gitbook 插件](http://localhost:4000/start/plugin.html) 里已经有100多个插件，可以在 `book.json` 文件的 `plugins` 和 `pluginsConfig` 字段添加插件及相关配置，添加后别忘了进行安装。

```
// book.json
{
  "title": "Webpack 中文指南",
  "description": "Webpack 是当下最热门的前端资源模块化管理和打包工具，本书大部分内容翻译自 Webpack 官网。",
  "language": "zh",
  "plugins": [
    "disqus",
    "github",
    "editlink",
    "prism",
    "-highlight",
    "baidu",
    "splitter",
    "sitemap"
  ],
  "pluginsConfig": {
    "disqus": {
      "shortName": "webpack-handbook"
    },
    "github": {
      "url": "https://github.com/zhaoda/webpack-handbook"
    },
    "editlink": {
      "base": "https://github.com/zhaoda/webpack-handbook/blob/master/content",
      "label": "编辑本页"
    },
    "baidu": {
        "token": "a9787f0ab45d5e237bab522431d0a7ec"
    },
    "sitemap": {
        "hostname": "http://zhaoda.net/"
    }
  }
}

```

```
# 安装插件
$ gitbook install ./
```

## [editlink](https://plugins.gitbook.com/plugin/editlink)

内容顶部显示 `编辑本页` 链接。

## [ad](https://plugins.gitbook.com/plugin/ad)

在每个页面顶部和底部添加广告或任何自定义内容。

## [splitter](https://plugins.gitbook.com/plugin/splitter)

在左侧目录和右侧内容之间添加一个可以拖拽的栏，用来调整两边的宽度。

## [image-captions](https://plugins.gitbook.com/plugin/image-captions)

抓取内容中图片的 `alt` 或 `title` 属性，在图片下面显示标题。

## [github](https://plugins.gitbook.com/plugin/github)

在右上角显示 github 仓库的图标链接。

## [anchors](https://plugins.gitbook.com/plugin/anchors)

标题带有 github 样式的锚点。

## [chart](https://plugins.gitbook.com/plugin/chart)

使用 C3.js 图表。

## [styles-sass](https://plugins.gitbook.com/plugin/styles-sass)

使用 SASS 替换 CSS。

## [styles-less](https://plugins.gitbook.com/plugin/styles-less)

使用 LESS 替换 CSS。

## [ga](https://plugins.gitbook.com/plugin/ga)

添加 Google 统计代码。

## [disqus](https://plugins.gitbook.com/plugin/disqus)

添加 disqus 评论插件。

## [sitemap](https://plugins.gitbook.com/plugin/sitemap)

生成站点地图。

## [latex-codecogs](https://plugins.gitbook.com/plugin/latex-codecogs)

使用数学方程式。

## [mermaid](https://plugins.gitbook.com/plugin/mermaid)

使用流程图。

## [book-summary-scroll-position-saver](https://plugins.gitbook.com/plugin/book-summary-scroll-position-saver)

自动保存左侧目录区域导航条的位置。

## [sharing](https://plugins.gitbook.com/plugin/sharing)

默认的分享插件。

## [fontsettings](https://plugins.gitbook.com/plugin/fontsettings)

默认的字体、字号、颜色设置插件。

## [search](https://plugins.gitbook.com/plugin/search)

默认搜索插件。

## [tbfed-pagefooter](https://plugins.gitbook.com/plugin/tbfed-pagefooter)

自定义页脚，显示版权和最后修订时间。

## [prism](https://plugins.gitbook.com/plugin/prism)

基于 [Prism](http://prismjs.com/) 的代码高亮。

## [atoc](https://plugins.gitbook.com/plugin/atoc)

插入 TOC 目录。

## [ace](https://plugins.gitbook.com/plugin/ace)

插入代码高亮编辑器。

## [highlight](https://plugins.gitbook.com/plugin/highlight)

默认的代码高亮插件，通常会使用 prism 来替换。

## [github-buttons](https://plugins.gitbook.com/plugin/github-buttons)

显示 github 仓库的 star 和 fork 按钮。

## [sectionx](https://plugins.gitbook.com/plugin/sectionx)

分离各个段落，并提供一个展开收起的按钮。

## [mcqx](https://plugins.gitbook.com/plugin/mcqx)

使用选择题。

## [include-codeblock](https://plugins.gitbook.com/plugin/include-codeblock)

通过引用文件插入代码。

## [fbqx](https://plugins.gitbook.com/plugin/fbqx)

使用填空题。

## [spoiler](https://plugins.gitbook.com/plugin/spoiler)

隐藏答案，当鼠标划过时才显示。

## [anchor-navigation](https://plugins.gitbook.com/plugin/anchor-navigation)

锚点导航。

## [youtubex](https://plugins.gitbook.com/plugin/youtubex)

插入 YouTube 视频。

## [redirect](https://plugins.gitbook.com/plugin/redirect)

页面跳转。

## [expandable-chapters](https://plugins.gitbook.com/plugin/expandable-chapters)

收起或展开章节目录中的父节点。

## [baidu](https://plugins.gitbook.com/plugin/baidu)

使用百度统计。

## [duoshuo](https://plugins.gitbook.com/plugin/duoshuo)

使用多说评论。

## [jsfiddle](https://plugins.gitbook.com/plugin/jsfiddle)

插入 JSFiddle 组件。

## [jsbin](https://plugins.gitbook.com/plugin/jsbin)

插入 JSBin 组件。

## 开发插件

最好先查看别人的插件是怎么做的，然后再看[官方文档](https://developer.gitbook.com/plugins/index.html)。

# 10. 配置

在book.json中配置，键值对的形式

- title 设置书本的标题

```json
"title" : "Gitbook Use"
```

- author 作者的相关信息

```json
"author" : "zhangjikai"
```

- description 书本的简单描述

```json
"description" : "记录Gitbook的配置和一些插件的使用"
```

- language Gitbook使用的语言, 版本2.6.4中可选的语言如下


```
en, ar, bn, cs, de, en, es, fa, fi, fr, he, it, ja, ko, no, pl, pt, ro, ru, sv, uk, vi, zh-hans, zh-tw
```

配置使用简体中文

```json
"language" : "zh-hans"
```

- links 在左侧导航栏添加链接信息

```json
"links" : {
    "sidebar" : {
        "Home" : "http://zhangjikai.com"
    }
}
```

- styles 自定义页面样式， 默认情况下各generator对应的css文件

```json
"styles": {
    "website": "styles/website.css",
    "ebook": "styles/ebook.css",
    "pdf": "styles/pdf.css",
    "mobi": "styles/mobi.css",
    "epub": "styles/epub.css"
}
```

例如使`<h1> <h2>`标签有下边框， 可以在`website.css`中设置

```json
h1 , h2{
    border-bottom: 1px solid #EFEAEA;
}
```

- plugins 配置使用的插件

```
"plugins": [
    "disqus"
]
```

添加新插件之后需要运行`gitbook install`来安装新的插件

Gitbook默认带有5个插件：

- highlight
- search
- sharing
- font-settings
- livereload

如果要去除自带的插件， 可以在插件名称前面加`-`

```json
"plugins": [
    "-search"
]
```

# 11. 解决 npm 的 shasum check failed for 错误

- https://segmentfault.com/a/1190000008073872
- http://www.uedbox.com/npm-install-slow-solution/

# 12. 更多GitBook教程

- [GitBook 中文解說 - 2.4](https://www.gitbook.com/book/wastemobile/gitbook-chinese/details)
- [gitbook-documentation](https://www.gitbook.com/book/zhanghqgit/gitbook-documentation/details)
- [gitbook-documentation](https://www.gitbook.com/book/chestnutme/gitbook-documentation/details)
