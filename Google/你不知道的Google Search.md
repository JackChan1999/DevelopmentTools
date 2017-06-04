## 0.导读

**文章讲3个事**

1.怎样访问Google?----------什么？不是直接输入地址么？

2.Google的地址是什么?------ 你在逗我？难道不是www.google.com?

3.Google Search的技巧------直接输入关键词不就行了么？那么复杂干嘛？

不要着急，且往下看...

## 1. 怎样访问Google？

确切的说，是怎样在中国大陆访问神奇的Google。

简单说，推荐配置如下：

1. Chrome/猎豹浏览器

2. 申请Google App Engine并创建appid

3. Goagent Assistant 配合Proxy Switchy Sharp扩展

### 1.1 Chrome/猎豹浏览器

知乎上关于这两个浏览器的讨论挺多，见仁见智，

你为什么喜欢用 Chrome？相较国产浏览器的优势在哪里？

猎豹浏览器比之 Google Chrome，是否性能更加强劲？为什么？

我觉得是个人习惯问题，用顺手了就行。

你问我用什么浏览器？我两个都用。

### 1.2 申请Google App Engine并创建appid

首先，送上官方教程链接：

申请Google App Engine并创建appid 的 官方图文教程链接，左键单击我

然后是无图版教程：

1. 申请注册一个Google App Engine账号https://appengine.google.com。没有Gmail账号先注册一个，用你的Gmaill账号登录。
2. 登录之后，自动转向Application注册页面
3. 接下来的页面，输入你的手机号码，需要注意的是，手机号码前面要+86（中国区号） 格式如：+86 13888888888。
4. 然后等待收取手机短信，收到短信后（一串数字号码）填入下图表单，点send提交.（有的手机收不到信息，解决办法：详细教程到https://appengine.google.com/waitlist/sms_issues提交该情况，一个工作日就能收到谷歌提示Google App Engine成功开通）。
5. 提交完成之后，GAE账号即被激活，然后就可以创建新的应用程序了。转入“My Applications”页面，点击“Create an Application”新建应用

### 1.3 Goagent Assistant 配合 Proxy Switchy Sharp扩展

#### 什么是Goagent Assistant？

Goagent Assistant是一个一键批处理辅助goagent自动更新程序：默认第一次安装会自动从官方网站上下载最新版goagent，并且自启动自动配置向导，就算是没有用过goagent的新手也可以轻松配置。

正常使用goagent_Assistant.exe，启动配置批处理，按0即可实现一键升级更新，翻墙方便快捷，会自动读取之前配置过的appid并导入，无需再手工下载配置。

并带有其他更多功能，网友们可以自己探索，全部用批处理实现，自解压包，懂批处理的可解压看到所有文件源码，安全可靠！

#### 自动配置安装Goagent Assistant：

1. 双击goagent_Assistant.exe，出现一个cmd窗口，提示可以拖放进去已经下载好的最新Goagent安装包，也可以直接回车自动下载最新的安装包。 直接回车。
2. 根据提示填写appid、email和password。

#### 安装Proxy Switchy Sharp扩展

地址栏输入chrome://extensions/后按回车，打开扩展管理页，将goagent_Assistant 安装目录中 local文件夹中的SwitchySharp-0.9-beta-r48.crx拖拽到该页面之后点击确定即可安装，扩展也可以从chrome应用商店获得https://chrome.google.com/webstore/detail/proxy-switchysharp/dpplabbmogkhghncfbfdeeokoefdjegm

#### 导入Proxy Switchy Sharp设置

1. 点击 Proxy SwitchySharp图标》选项》导入/导出》
2. 浏览到SwitchyOptions.bak，点击确定导入设置
3. 更新自动切换规则（如果遇到无法更新规则列表，可以先运行goagent，并把浏览器代理设置为GoAgent模式再更新规则，不更新规则只会影响自动切换模式，不会影响其他模式的使用，若确实无法更新也可不更新，直接使用PAC模式即可）
4. 在扩展设置页点击“切换规则”，点击“立即更新列表”，最后点击“保存”。

#### Proxy Switchy Sharp模式选择

1. 单击地址栏右侧Proxy SwitchySharp图标即可进行模式选择
2. GoAgent模式 除匹配proxy.ini中sites的直连外，其他全部通过GAE
3. GoAgent PAAS模式 全部通过PAAS
4. GoAgent PAC模式 根据GoAgent自带的PAC文件自动判断是否经过代理
5. 自动切换模式 根据切换规则自动选择是否进行代理，并根据所设情景模式自动选择使用何种代理

安装完成后，不需要再进行配置。如需更改，运行桌面上的Goagent图标：

1、自动代理模式：国内网站无需走代理，只有被墙的地址才会走代理，推荐此模式；

2、全局代理模式：无论任何网站都走代理。

3、停用代理：退出Goagent并自动去除internet代理设置；

4、清理临时文件：一键清除IE缓存及访问记录。

5、导入证书：自动导入Goagent CA证书到系统。

6、配置appid：请填写配置您自己的appid，将自动帮你写入到proxy.ini配置文件中。

7、使用公共id：如果您暂时没有申请appid，可以选择此项，将会自动帮你导入公共appid以便临时使用。

8、上传server端：将会弹出uploader.bat，请根据提示输入appid、gmail邮箱和密码进行服务端的更新、部署与上传。

9、设置开机启动：设置Goagent开机自启动。

10、自动更新：一键式更新到当前最新版本，更新自动读取当前配置，无需再行手工修改配置。

11、退出：退出当前批处理界面，不影响Goagent的正常运行。

Goagent常见问题 FAQ

## 2. Google的地址是什么?

### 2.1 Google 真身

首先，不同国家的人们访问的Google是不一样的，如果你不去管它的话。

以下引用自Google网页搜索帮助：

为了方便我们向您提供最相关的搜索结果，Google 针对全球多个国家和地区分别自定义了 Google 网页搜索。例如，Google.fr提供与法国用户最为相关的搜索结果。我们尽量将用户定向至能为他们提供最相关结果的网站。如果我们将您引导至错误的网站，您有许多办法可以进入自己喜欢的 Google 网页。

那么，如何访问 Google.com 而不是您的本地域呢？

http://www.google.com/ncr这是 Google.com 的辅助网址，可随时将您导向 Google.com（无需重定向）。

把这个网址添加到收藏吧，你会喜欢它的。

### 2.2 Google 台湾

www.google.com.tw

推荐理由：中文语言，搜素技术资料时能搜到台湾的资料

## 3. Google Search的技巧

### 3.1 搜索运算符

您可以在搜索中添加称为搜索运算符的符号和字词，从而减少搜索结果的数量。不必担心需要记住每一个运算符，因为您也可以使用高级搜索页面来进行这种搜索。

使用运算符进行搜索时，请不要在运算符和查询内容之间添加任何空格。搜索site:nytimes.com可以获取相关搜索结果，而搜索site: nytimes.com则是行不通的。

- 搜索精确字词或词组:“搜索”

使用引号来精确搜索网页上的字词或词组。通过这种方法可迅速搜索到歌词或书中的一段文字。  不过，建议您仅在需要搜索某个精确字词或词组时使用这种搜索方式，不然，可能会错误地排除掉很多有用的搜索结果。  “想象一下所有的人”

- 排除字词:-搜索

在某个字词或网站之前添加一个减号(-)可排除所有包含该字词的搜索结果。  在搜索有多种含义的字词（例如“汽车品牌捷豹”和“动物捷豹”）时，这种方法尤为实用。  捷豹速度 -汽车 

熊猫 -site:wikipedia.org

- 搜索特定文件类型: filetype:

想搜索一篇关于最新材料技术的Word论文，使用Google搜索“filetype:doc 材料技术 ”

- 在特定网站或网域中搜索: site:

仅从特定网站或网域获得搜索结果。 例如，你可以找到中央电视台网站或任何.gov网站上所有提到“奥运”的内容。 奥运 site:cctv.com 奥林匹克site:.gov

- 搜索链接到某网址的页面:link:

查找链接到某个特定网页的页面。例如，您可以查找链接到google.com.hk的所有页面。  link:google.com

- 搜索与某网址相似的页面: related:

查找与您已浏览过的网址类似的网站。 当您搜索与Time.com相关的网站时，会找到您可能感兴趣的其他新闻出版物网站。  related:time.com

- 加入占位符:星号

在搜索中添加一个星号，以表示任何未知或不确定的字词。 使用引号可以查找准确词组的不同变体，或记住词组中间的字词。 “省*就是赚*”

- 搜索选择性字词： OR

如果您想搜索可能只包含多个搜索字词中某一个的页面，可以在这些字词之间加上OR（大写）。 如果不加OR，您的搜索结果中通常只会显示与这些字词都匹配的页面。 世界杯举办地2014年OR2018年

- 搜索数字范围：..

使用不含空格的两个半角句号(..)隔开多个数字，就可查看包含日期、价格和尺寸等指定范围内数值的搜索结果。 相机50美元..100美元

- 搜索某网站的相关信息： info

获取某网址的相关信息，包括网页的缓存版本、相似网页和链接至该网站的网址。 info:google.com

- 查看网站的缓存版本： cache:

查看Google上次抓取的网站的网页外观。  cache:washington.edu

![img](http://mmbiz.qpic.cn/mmbiz/rOeDV5Q9ZqAD2sibj6U7Ry3gWdXKhtqhTFP4hR1ovUICbERPm2zzsUNy1SITy7KsP1QRI6vlp8Ppu8ju3QictHAA/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1)

### 3.2搜索中的标点和符号

[+] 用于搜索类似血型（例如[AB+]）的内容或Google+信息页（例如[+Chrome]

[@] 用于查找社交标记，例如[@google]

[&] 用于紧密关联主题和词组，例如[A&E]

[%] 用于搜索百分比值，例如[40% of 80]

`[$] `用于表示价格，例如[nikon $400]

[#] 用于搜索以哈希标记（例如 [##lifewithoutgoogle]

[-] 用于表示搜索字词周围的字词紧密关联，例如[twelve-year-old dog]

[_] 用于连接两个字词，例如[quick_sort]。您会在搜索结果中发现，这对字词要么组成一个字词(quicksort)，要么由下划线相连(quick_sort)。

### 3.3高级搜索

借助“高级搜索”页，您可以缩小复杂搜索查询的搜索结果的范围。

例如，您可以查找以西班牙语撰写、标题中包含“Paella”并且在过去24小时之内更新过的网站，或者查找纽约的黑白图片。

“高级搜索”页的工作原理

在“使用以下条件来搜索网页”部分输入您的搜索字词。

在“然后按以下标准缩小搜索结果范围”部分选择您要使用的过滤条件。您可以使用一个或多个过滤条件。

点击高级搜索。