# 使用 Calibre 管理和转换电子出版物

**让文档更易于使用**

如今大多数产品文档和文献都是以 PDF 格式传播的，很多书籍也有了各种各样的电子出版格式。针对智能手机、便携式计算机和平板电脑，都有相应的应用程来阅读这些文档。比方说一些专门的 eBook 阅读器，比如 Kindle、Nook 和 Kobo eReader。遗憾的是这些 eBook 阅读器支持不同的电子出版格式，从而限制了这些电子出版物在设备上的使用。本文将向您介绍一种开源应用程序 Calibre，让您可以在书和文档的多种格式间相互转换。

## 电子出版：绿色而且方便

对于如今的移动办公人员和总是在线的一族而言，保持对信息的访问是一个基本要求。基于 Web 的内容很自然地可以从任何安装有浏览器的联网的移动设备读取，但是较长的内容一般以各种电子出版格式本地存储于移动设备或便携式设备 会更为方便。

鉴于像平板电脑、智能手机和 eBook 阅读器这样的设备的普遍存在，更多的组织都开始以电子出版的格式来发布产品文献和文档以供内部用户和外部客户使用。发布电子文档能让客户更快地获得这些文档并可以省钱、省纸和简化文档更新。通过让客户能更多地控制在哪里以及如何访问电子文档，电子出版为消费者和出版商提供了直接的好处。

## 便携出版中的问题

电子出版解决了发布和访问文档时的很多问题，但也引入了一个新的问题：电子内容的交付格式。[表 1](https://www.ibm.com/developerworks/cn/opensource/os-calibre/#table1) 列出了很多常用的电子出版格式及支持这些格式的设备，但是还有很多其他的格式可用。正如此表所示，所有的电子文档阅读器（无论是应用程序还是专用设备）支持的都只是这些格式中有限的几个。当手动创建电子内容时，企业出版商必须选择 “正确的” 电子出版格式，至少是那些在内部以及由顾客使用的设备和应用程序支持的格式。

**表 1. 电子出版格式及支持设备**

| 格式   | 描述                                       | eReader 支持                               |
| :--- | ---------------------------------------- | :--------------------------------------- |
| TXT  | 纯文本格式                                    | 全部                                       |
| HTML | 超文本标记语言                                  | 绝大多数例外：Barnes & Noble Nook               |
| PDF  | Adobe® 可移植文档格式非移动友好， 除非在文档创建期间启用了文本重排。   | 大多数                                      |
| EPUB | 广受支持的电子出版开放格式更多信息，请参见 [参考资料](https://www.ibm.com/developerworks/cn/opensource/os-calibre/#resources)。 | 大多数例外：Amazon Kindle                      |
| MOBI | 遵循 Open eBook (OEB) 格式的规范还可以有 PRC (Palm) 或 AZW (Amazon DRM-enabled MOBI) 扩展 | 大多数例外：Nook                               |
| LIT  | 微软的文献格式                                  | 仅限微软® Reader 应用程序                        |
| PDB  | 指的是不同设备上的不同格式                            | Sony Reader、开源 Plucker 应用程序、Palm 及兼容设备上的 TealDoc 文档 |

免费和开源的 Calibre 应用程序可充当所有这些不同的格式的一个便利的翻译程序。Calibre 是一个开源的应用程序，让您可以将电子出版物从一种格式转变成另一种格式，将电子文档从特定的格式或设备的局限中解放出来。Calibre 可以读取所有常见的电子出版格式以及 PDF、文本及 HTML 格式的导入文档。然后您可以使用 Calibre 的转换功能将这些导入文档保存成所需要的特定格式。

企业出版商应当谨记，转换不同的格式的电子出版物供公司使用可能需要购买这些文档的额外副本。如果有这方面的疑问，可以先咨询您公司的法律人员，然后再对非您公司所有的电子文档进行转换和重新发布。转换不同格式的电子文档供个人使用通常会被视作是合理使用，只要您不要删除在这些文档内存在的任何 DRM 机制且尊重原始出版者施加的再发行的限制。

## 获取并安装 Calibre

Calibre 针对 Windows® 和 Apple Mac OS X 操作系统的安装版本可以从 Calibre 下载页（参见 [参考资料](https://www.ibm.com/developerworks/cn/opensource/os-calibre/#resources)）获得。Calibre for Linux® 则是作为一个包在大多数的 Linux 发行版的存储库内提供的，且可以使用您的发行版的包管理实用工具安装，通常是 `apt-get`、`rpm`、Synaptic 或 `yum`。如果您的发行版的存储库不包括 Calibre 的预打包版，或者是您想要安装比 Linux 发行版内提供的 Calibre 版本更新的一个版本，那么可以使用如下命令从 Internet 下载并安装 Calibre 的最新版本：

```
python -c "import urllib2; \
  exec urllib2.urlopen('http://status.calibre-ebook.com/linux_installer').read(); main()"
```

必须以特权用户身份执行这个安装命令，且在使用 `su` 或 `sudo` 时，必须在一行内键入，且没有反斜杠符号 （`\`，在本例中用于格式化的目的）。

输入此命令后，针对 Linux 的最新的 Calibre 版本就会下载到您的系统中。系统之后就会提示输入想要将 Calibre 安装到其中的目录：

```
Enter the installation directory for calibre [/opt]:
```

输入目录的名称，安装程序会在这个目录下创建一个 Calibre 子目录来保存 Calibre 及相关应用程序、数据文件和库。您也可以仅简单地单击 **Return** 来接受默认值 /opt，这会创建 /opt/calibre 目录并将 Calibre 安装在该位置。通过 Internet 安装 Calibre 会在系统的 /usr/bin 目录下创建符号链接，指向 Calibre 包内的 Calibre 应用程序及其他的应用程序。

### 将文档导入到一个 Calibre 库

Calibre 是一个图形应用程序，它使用 QT UI Framework（参见 [参考资料](https://www.ibm.com/developerworks/cn/opensource/os-calibre/#resources)）来提供标准的跨平台的 GUI。安装 Calibre 还会提供大量命令行工具，稍后讨论。

在图形模式下使用 Calibre 时，必须先将现有的文档导入到 Calibre 库，然后才能对之进行转换、注释或修改。要选择想要导入的文档，单击 Calibre 工具栏上的 **Add books** 图标。在所出现的导航窗口，浏览并选择这些文档，然后再单击 **Open** 导入这些文档。

Calibre 的主窗口会显示 Calibre 库内有关现有文档的总结信息。在第一次启动 Calibre 时，这个列表只包含了 Calibre Quick Start Guide，它通过带您亲历 Calibre 的基本功能来帮助您开始使用 Calibre。在将文档导入到 Calibre 库后，此总结列表还会显示这些文档中的各个项目，如 [图 1](https://www.ibm.com/developerworks/cn/opensource/os-calibre/#fig1) 所示。

**图 1. 显示所导入文档的主 Calibre 窗口**

![](https://www.ibm.com/developerworks/cn/opensource/os-calibre/calibre-doc-listing.jpg)

选择库中的任何一个文档都会在右侧的面板中显示该文档的预览。该文档目前可用的输出格式会在预览图像之下列出。

在将文档导入到 Calibre 后，就可以单击其工具栏内的图标来执行各项任务，比如将这些文档转换成其他格式、添加或扩充文档元数据。参见 Calibre 文档或在线帮助，获取工具栏图标及其关联任务的完整列表。

### 转换文档的电子格式

利用 Calibre 的 **Convert books** 工具栏图标可以方便地将 Calibre 库内的文档转换成其他的电子格式。 选择库内的一个或多个文档并单击这个图标会显示出 Calibre 的主转换窗口，如 [图 2](https://www.ibm.com/developerworks/cn/opensource/os-calibre/#fig2) 所示。

**图 2. Calibre 的主转换窗口**

![](https://www.ibm.com/developerworks/cn/opensource/os-calibre/calibre-convert.jpg)

左上角的 **Input format** 列表给出了所选文档的格式，而右侧的 **Output format** 列表则让您能够从中选择想要将该文档转换到的电子出版格式。使用左侧窗格内的按钮可定制特定于此输入和输出格式的这一转换过程的各个方面。这些选项可让您定制默认的转换过程，例如，通过指定逻辑表达式来标识此输入文档的哪些部分应被视作转换后的这个文档的目录中的项。

当完成了对转换过程的定制后，单击 **OK** 在后台开始转换并重新显示这个主 Calibre 窗口。在左下角的状态指示器标识了进行中的转换操作的数量。过程完成后，Calibre 就会更新文档可用的输出格式列表以包括进这些新生成的格式。

## 使用 Calibre 添加或修改文档元数据

*元数据* 通常又被称为有关数据的数据，它指的是有关另外一条信息的信息。文档通常包含这样一些元数据，比如作者、出版商以及出版日期。利用 Calibre 的 **edit metadata** 命令可方便地显示与所选文档相关的当前元数据，让您可以添加、编辑或删除文档元数据。选择库内的一个文档并单击 **Edit metadata** 图标会显示 Calibre 的 **Edit Metadata** 窗口，如 [图 3](https://www.ibm.com/developerworks/cn/opensource/os-calibre/#fig3) 所示。

**图 3. Calibre 的 Edit Metadata 窗口**

![](https://www.ibm.com/developerworks/cn/opensource/os-calibre/calibre-metadata.jpg)

要添加新的元数据或编辑现有的项，选择适当的字段后就可以进行这些更改或添加了。单击 **OK** 将所修改的元数据保存在文档内，或单击**Cancel** 丢弃这些更改。

## 使用 Calibre 的命令行实用工具自动化电子出版

安装 Calibre 时还会附带安装一些用来处理电子出版物的命令行工具。这些工具包括可用来转换文档 的 `ebook-convert` 应用程序及用来添加或修改文档元数据的 `ebook-meta` 应用程序。Calibre 的命令行实用工具消除了将文档导入到 Calibre 库的需要，而且对于正在将文档转换或自动元数据插入集成到一个自动化了的文档构建或生产系统的情形非常方便实用。

Calibre 的命令行实用工具提供了与其 GUI 相同的功能，通过命令行选项及相关参数可以启用或重写特定的行为。每个命令行实用工具都提供了一个 `-h` 选项来显示对该命令可用的选项列表。例如，要查看对转换过程可用的选项的完整列表，可以执行 `ebook-convert` 命令；指定输入文档、输出文档及相关格式（由文件扩展名标识）；并提供 `-h` 选项。

## 电子文档转换的技巧及其他工具

Calibre 提供了转换过程可用的默认设置，但是自动格式转换很少是完美的。将文档转换成其他格式通常都需要用可用的转换选项反复试验，这常常会涉及到进行一次初始转换、显示转换后的文档来查找转换过程中的问题或待改进的地方、修改转换设置后重新转换文档。

转换过程待改进的主要地方通常都是如何标识目录内的各项以及如何创建与文档相关的各部分的链接。[图 4](https://www.ibm.com/developerworks/cn/opensource/os-calibre/#fig4) 显示了 Calibre 文档预览器内的一个转换后的文档，这就让您无需将转换后的文档复制到 eReader 设备就可以对它们进行探究。

**图 4. Calibre eBook 预览器内的一个转换后的文档**

![](https://www.ibm.com/developerworks/cn/opensource/os-calibre/calibre-preview.jpg)

改进转换过程的其他方式还包括使用其他工具来执行到另一格式的初始转换，这一格式可能更易于 Calibre 进行转换。例如，在转换篇幅较长的技术文档时，有时我发现，在从 PDF 格式的文档提取文本时，作为 `poppler-utils` 包的一部分在 Linux 系统上提供的开源 `pdftohtml` 实用工具要比 Calibre 内置的文本到 HTML 转换做得更好。在用外部工具手动转换文档后，就可以使用 Calibre 从初始转换过程生成的那些输出文件生成电子文档。

现在已经有很多其他的开源工具可用来预转换或扩充和改进 Calibre 所转换的文档。例如，Sigil 是一个用于 EPUB 格式的文档的图形 WYSIWYG 编辑器，可简化已转换文档的调优，如 [图 5](https://www.ibm.com/developerworks/cn/opensource/os-calibre/#fig5) 所示。（查看 [图 5 的放大版本](https://www.ibm.com/developerworks/cn/opensource/os-calibre/sidefile-figure5lrg.html)。）

**图 5. 在 Sigil 内调优已转换的 EPUB 文档**

![](https://www.ibm.com/developerworks/cn/opensource/os-calibre/sigil.jpg)

您可能会感觉编辑已转换文档会减少 Calibre 的文档转换功能所能提供的时间和成本上的节省。然而，用像 Sigil 这样的工具探索转换后的文档还能帮助找到改进转换过程的一些方式。同样地，通过使用电子出版物最初创建所用的那个工具内的特定技术通常也能改进转换过程。为了举例说明，[参考资料](https://www.ibm.com/developerworks/cn/opensource/os-calibre/#resources) 部分提供了一些链接，所链向的这些演示文件展示了如何改进 Adobe InDesign® 内创建的电子文档的转换。虽然这些技巧多关注于内部的 EPUB 生成和转换功能，但在使用其他的转换工具，比如 Calibre 时，它们也非常有用。

## 结束语

与传统的出版商一样，组织们发现发布电子格式的文档既方便又节约成本。如今的电子出版技术可以交付各种格式的 eBooks 和其他文档，但并不是所有格式在所有 eReader 和应用程序上都是可用的。

开源应用程序 Calibre 简化了文档在不同电子出版格式间的转换。组织可以创建一种格式的文档，然后使用 Calibre 来快速地将其转换成其他格式，从而使这些文档既便携又方便内部用户和外部客户使用。

## 参考资料

### 学习

- 访问 [Calibre 网站](http://calibre-ebook.com/) 获得 Calibre 的最新版本、视频教程、演示和其他有关 Calibre 的最新信息。
- 了解有关 Nokia 的 [Qt UI Framework](http://qt.nokia.com/) 的更多信息。
- 如果您使用 InDesign 准备公司文档，请参见 [Preparing your InDesign files for ePub export](http://labs.oreilly.com/Bilodeau-IDtoEPub.pdf) 和 [Using InDesign to create eBooks](http://thebookstudio.files.wordpress.com/2011/05/bostonidug2011.pdf) 获得有关简化导出及将 InDesign 文档转换成 EPUB 格式的技巧。
- 访问 [International Digital Publishing Forum](http://www.idpf.org/) 站点获得有关数字出版行业现有及未来标准的信息。
- 随时关注 developerWorks [技术活动](http://www.ibm.com/developerworks/cn/offers/techbriefings/)和[网络广播](http://www.ibm.com/developerworks/cn/swi/)。
- 访问 developerWorks [Open source 专区](http://www.ibm.com/developerworks/cn/opensource/)获得丰富的 how-to 信息、工具和项目更新以及[最受欢迎的文章和教程](http://www.ibm.com/developerworks/cn/opensource/best2009/index.html)，帮助您用开放源码技术进行开发，并将它们与 IBM 产品结合使用。

### 获得产品和技术

- 从 [Calibre Windows 下载页](http://calibre-ebook.com/download_windows) 下载 Calibre 针对 Windows 操作系统的安装程序。
- 从 [Mac OS X 下载页](http://calibre-ebook.com/download_osx)下载 Calibre 针对 Mac OS X 的最新安装程序。Calibre 针对 Apple PowerPC 系统或 运行 Mac OS X Tiger 的基于 Intel 的 Apple 系统的最新版本是 0.7.28，可分别从 [Calibre site at SourceForge](http://sourceforge.net/projects/calibre/files/0.7.28/calibre-0.7.28.dmg/download) 获得。
- LexCycle 的免费 [Stanza 应用程序](http://www.lexcycle.com/) 让您可以在 Apple iPod Touch、iPhone 和 iPad 平台上阅读电子出版物。
- 参见 `pdftohtml` 实用工具的 [`poppler-utils`](http://poppler.freedesktop.org/) 网站和包，该工具可简化从 PDF 文件提取文本。
- [Sigil](http://code.google.com/p/sigil/) 是一个面向 ePub 格式的 eBooks 的免费跨平台 WYSIWYG 编辑器。

### 讨论

- 加入 [developerWorks 中文社区](http://www.ibm.com/developerworks/cn/community/)，developerWorks 社区是一个面向全球 IT 专业人员，可以提供博客、书签、wiki、群组、联系、共享和协作等社区功能的专业社交网络社区。
- 加入 [IBM 软件下载与技术交流群组](https://www.ibm.com/developerworks/mydeveloperworks/groups/service/html/communityview?communityUuid=38997896-bb16-451a-aa97-189a27a3cd5a/?lang=zh)，参与在线交流。