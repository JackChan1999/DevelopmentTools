**AndroidXRef**

借助 Eclipse 以及本地源码可以比较方便地分析 Android 源码，但是对于 Native 代码的调
用就无法通过 Eclipse 的快速定位来查看相应的 Native 源码了，而且 Android 源码中对 Native
库的加载一般不是通过在 Static 块里调用 System.loadLibrary 来加载库文件并完成 Native 函数
注册的，所以定位这类代码比较困难。一个可以采取的方法是使用 UltraEdit 等工具来在文件
中搜索特定的字符串，如函数名，对于 JNI 函数来说，一般存在于/frameworks/base/core/jni
目录下。在文件数目较多的情况下，使用这种方法搜索起来还是比较忙的，所以这里介绍下
AndroidXRef。

AndroidXRef(http://androidxref.com/)项目提供 Android 源码的交叉索引，可以快速的搜索
符合特定条件的 Android 源代码，后台是基于 OpenGrok 引擎，OpenGrok 主要用来在源码中搜
索、交叉索引以及进行导航。AndroidXRef 提供了完整的 Android 源码的索引，包括内核源码。
在 AndroidXRef 主页的右侧显示了可用的源码版本，如图 9 所示，点击相应的源码版本链接
就可以进入对应的源码分支，如图 10 所示。 

![img](http://bbs.pediy.com/upload/attach/201401/444052_e0d19hz9loyxalq.png)
**图 9 AndroidXRef 主页**

![img](http://bbs.pediy.com/upload/attach/201401/444052_cj3nakkbpipmpa7.png)
**图 10 AndroidXRef KitKat4.4-r1 分支**

图 10 右侧提供在特定目录下搜索，例如在分析 Framework 时，可以选择 frameworks 目
录，这样可以减少搜索范围，能够更加精确地定位到需要的源代码。左侧则是提供了一些搜
索的条件，其意义如下(在指定的 Project(s)下)：

## Full Search:

进行全文搜索，会匹配所有的单词、字符串、标识符以及数字等，例如在
frameworks 下通过 Full Search 搜索”activity”，则会显示所有包含 activity 字符(忽略大小写)
的结果，即使是注释也会显示出来，如图 11 所示。点击绿色背景的链接会打开包含
activity 字符串文件所在的文件夹；点击左侧文件名如 WidgetAdder.java 链接会打开包含
activity 字符串文件；点击右侧每一行的搜索结果链接同样会打开相应的文件内容；

![img](http://bbs.pediy.com/upload/attach/201401/444052_lyr23rxju0zl88o.png)
**图 11 Full Search 搜索**

## Definition

搜索符号定义相关的代码，例如搜索 startActivityIfNeeded 函数的定义，显示
结果如图 12 所示，从搜索结果可以看到，右侧绿色字体表明了是位于 Activity 类中的 
方法；

![img](http://bbs.pediy.com/upload/attach/201401/444052_itx2cfb2a8ah7kv.png)
**图 12 Definition 搜索**


Symbol：搜索符号，例如可以搜索类中的成员变量等，图 13 显示了通过 Symbol 搜索
WINDOW_HIERARCHY_TAG 的结果；

![img](http://bbs.pediy.com/upload/attach/201401/444052_r3yvhis054mradm.png)
**图 13 Symbol 搜索**

## File Path

搜索源码文件名中包含给定字符串的文件，例如想要搜索文件名包含 Activity
的源码文件，则可以在 File Path 中填入 Activity 进行搜索，结果如所示；

![img](http://bbs.pediy.com/upload/attach/201401/444052_0xtmpigma5rrzu1.png)
**图 14 File Path 搜索**

## History

在 Git 库中的 history log comments 中搜索给定的字符串，这个用处应该不是特
别大，只是从 Android 源码提交者的 comments 中搜索信息。例如搜索 god 字符串，显
示结果如图 15 所示，但是点击源码文件链接，只是会显示源码内容，并不会附加 history
log comments 内容；

![img](http://bbs.pediy.com/upload/attach/201401/444052_m7h1xuz3b0k5jhv.png)
**图 15 History 搜索**

当然可以通过组合的方式使用上述提到的搜索方法，例如想在 Activity.java 文件中搜索
finish 函数的定义，则可以在 Definition 中填入”finish”，在 File Path 中填入”Activity.java”，搜索
结果如图 16 所示。
![img](http://bbs.pediy.com/upload/attach/201401/444052_e9btxeqy5kefyai.png)
**图 16 组合搜索**
因为 AndroidXRef 使用的是 OpenGrok 引擎，因此还支持一些其他的搜索方式：
+ 表示包含此字符串，- 表示包含此字符串。例如在 Full Search 中搜索包含 activity
  字符串但是不包含 service 字符串的源文件，可以填入+”activity” -“service”(去掉双引
  号同样可以，但是对于不可分割的词且两者间包含空格则双引号不可去，此规则适
  用于所有的搜索规则，例如 Full Search “final String”，双引号去除表示或的关系，这
  个与 Google 的搜索规则是一样的)；
  布尔操作，可以使用 AND(&&),”+”,OR(||),NOT(!)以及”-”(AND 等必须全部大写)，例如搜
  索既包含 final 又包含 String 的源码文件，可以 Full Search 中填入”final” AND “String”;
  使用通配符，”?”代表一个字符，”*”代表多个字符(“?”和”*”不可用于字符串的开头)；
  模糊查询，可以使用”~”搜索包含与提供的字符串拼写类似的源码文件等内容；
  转义字符，OpenGrok 中使用到的特殊字符包括+ - && || ! ( ) { } [ ] ^ " ~ * ? : \ ，因此如果需要搜索的内容中包含这些特殊字符，可以使用\进行转义，例如搜索(1+1):2，
  可以这样\(1\+1\)\:2。


更加详细的使用规则可以参考 AndroidXRef 的 Help(http://androidxref.com/4.4_r1/help.jsp)。

个人觉得 AndroidXRef 适合用来搜索定位源码文件的路径，至于源码的实际分析当然借
助于 Eclipse 等 IDE 会更加方便。