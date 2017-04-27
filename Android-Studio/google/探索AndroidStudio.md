Android Studio 是基于 [IntelliJ IDEA](https://www.jetbrains.com/idea/) 的官方 Android 应用开发集成开发环境 (IDE)。除了 IntelliJ 强大的代码编辑器和开发者工具，Android Studio 提供了更多可提高 Android 应用构建效率的功能，例如：

- 基于 Gradle 的灵活构建系统
- 快速且功能丰富的模拟器
- 可针对所有 Android 设备进行开发的统一的环境
- Instant Run，可将变更推送到运行中的应用，无需构建新的 APK
- 可帮助您构建常用应用功能和导入示例代码的代码模板和 GitHub 集成
- 丰富的测试工具和框架
- 可捕捉性能、可用性、版本兼容性以及其他问题的 Lint 工具
- C++ 和 NDK 支持
- 内置对 [Google 云端平台](http://developers.google.cn/cloud/devtools/android_studio_templates/)的支持，可轻松集成 Google Cloud Messaging 和 App 引擎

本页介绍了 Android Studio 的基本功能。 有关最新变更摘要，请参阅 [Android Studio 发行说明](https://developer.android.google.cn/tools/revisions/studio.html)。

## 1. 项目结构

![**图 1.** Android 视图中的项目文件](https://developer.android.google.cn/studio/images/intro/project-android-view_2-1_2x.png)

**图 1.** Android 视图中的项目文件。

Android Studio 中的每个项目包含一个或多个含有源代码文件和资源文件的模块。 模块类型包括：

- Android 应用模块
- 库模块
- Google App 引擎模块

默认情况下，Android Studio 会在 Android 项目视图中显示您的项目文件，如图 1 所示。 该视图按模块组织结构，方便您快速访问项目的关键源文件。

所有构建文件在项目层次结构顶层 **Gradle Scripts** 下显示，且每个应用模块都包含以下文件夹：

- **manifests**：包含 `AndroidManifest.xml` 文件。
- **java**：包含 Java 源代码文件，包括 JUnit 测试代码。
- **res**：包含所有非代码资源，例如 XML 布局、UI 字符串和位图图像。

磁盘上的 Android 项目结构与此扁平项目结构有所不同。 要查看实际的项目文件结构，可从 **Project** 下拉菜单（在图 1 中显示为 **Android**）选择 **Project**。

您也可以自定义项目文件的视图，重点显示应用开发的特定方面： 例如，选择项目的 **Problems** 视图会显示指向包含任何已识别编码和语法错误（例如布局文件中缺失一个 XML 元素结束标记）的源文件的链接。

![img](https://developer.android.google.cn/studio/images/intro/problems-view_2-1_2x.png)

**图 2.** Problems 视图中的项目文件，显示存在问题的布局文件。

如需了解详细信息，请参阅[管理项目](https://developer.android.google.cn/tools/projects/index.html)。

## 2. 用户界面

Android Studio 主窗口由图 3 标注的几个逻辑区域组成。

![img](https://developer.android.google.cn/studio/images/intro/main-window_2-1_2x.png)

**图 3.** Android Studio 主窗口。

1. **工具栏**提供执行各种操作的工具，包括运行应用和启动 Android 工具。
2. **导航栏**可帮助您在项目中导航，以及打开文件进行编辑。 此区域提供 **Project** 窗口所示结构的精简视图。
3. **编辑器窗口**是创建和修改代码的区域。 编辑器可能因当前文件类型的不同而有所差异。 例如，在查看布局文件时，编辑器显示布局编辑器。
4. **工具窗口**提供对特定任务的访问，例如项目管理、搜索和版本控制等。 您可以展开和折叠这些窗口。
5. **状态栏**显示项目和 IDE 本身的状态以及任何警告或消息。

您可以通过隐藏或移动工具栏和工具窗口调整主窗口，以便留出更多屏幕空间。 您还可以使用键盘快捷键访问大多数 IDE 功能。

您可以随时通过按两下 Shift 键或点击 Android Studio 窗口右上角的放大镜搜索源代码、数据库、操作和用户界面的元素等。此功能非常实用，例如在您忘记如何触发特定 IDE 操作时，可以利用此功能进行查找。

### 工具窗口

Android Studio 不使用预设窗口，而是根据情境在您工作时自动显示相关工具窗口。 默认情况下，最常用的工具窗口固定在应用窗口边缘的工具窗口栏上。

- 要展开或折叠工具窗口，请在工具窗口栏中点击该工具的名称。 您还可以拖动、固定、取消固定、关联和分离工具窗口。
- 要返回到当前默认工具窗口布局，请点击 **Window > Restore Default Layout** 或点击 **Window > Store Current Layout as Default** 自定义默认布局。
- 要显示或隐藏整个工具窗口栏，请点击 Android Studio 窗口左下角的窗口图标 ![img](https://developer.android.google.cn/studio/images/intro/window-icon_2-1_2x.png)。
- 要找到特定工具窗口，请将鼠标指针悬停在窗口图标上方，并从菜单选择相应的工具窗口。

您也可以使用键盘快捷键打开工具窗口。 表 1 列出了最常用的窗口的快捷键。

**表 1.** 部分实用工具窗口的键盘快捷键。

| 工具窗口            | Windows 和 Linux       | Mac                   |
| :-------------- | :-------------------- | :-------------------- |
| 项目              | **Alt+1**             | **Command+1**         |
| 版本控制            | **Alt+9**             | **Command+9**         |
| 运行              | **Shift+F10**         | **Control+R**         |
| 调试              | **Shift+F9**          | **Control+D**         |
| Android Monitor | **Alt+6**             | **Command+6**         |
| 返回至编辑器          | **Esc**               | **Esc**               |
| 隐藏所有工具窗口        | **Control+Shift+F12** | **Command+Shift+F12** |

如果您想要隐藏所有工具栏、工具窗口和编辑器选项卡，请点击 **View > Enter Distraction Free Mode**。 此操作可启用*无干扰模式*。 要退出“无干扰模式”，请点击 **View > Exit Distraction Free Mode**。

您可以使用*快速搜索*在 Android Studio 中的大多数工具窗口中执行搜索和筛选。 要使用快速搜索，请选择工具窗口，然后键入搜索查询。

如需了解更多技巧，请参阅[键盘快捷键](https://developer.android.google.cn/studio/intro/keyboard-shortcuts.html)。

### 代码自动完成

Android Studio 有三种代码自动完成类型，您可以使用键盘快捷键访问它们。

**表 2.** 代码自动完成的键盘快捷键

| 类型     | 说明                                       | Windows 和 Linux         | Mac                     |
| :----- | :--------------------------------------- | :---------------------- | :---------------------- |
| 基本自动完成 | 显示对变量、类型、方法和表达式等的基本建议。 如果连续两次调用基本自动完成，将显示更多结果，包括私有成员和非导入静态成员。 | **Control+空格**          | **Control+空格**          |
| 智能自动完成 | 根据上下文显示相关选项。 智能自动完成可识别预期类型和数据流。 如果连续两次调用智能自动完成，将显示更多结果，包括链。 | **Control+Shift+空格**    | **Control+Shift+空格**    |
| 语句自动完成 | 自动完成当前语句，添加缺失的圆括号、大括号、花括号和格式化等。          | **Control+Shift+Enter** | **Shift+Command+Enter** |

您还可以按 **Alt+Enter** 执行快速修复并显示建议的操作。

如需了解有关代码自动完成的详细信息，请参阅[代码自动完成](https://www.jetbrains.com/help/idea/2016.1/code-completion-2.html)。

### 导航

以下是一些操作 Android Studio 的技巧。

- 使用*最近文件*操作在最近访问的文件之间切换。 按 **Control+E**（在 Mac 上，按 **Command+E**）调出“最近文件”操作。 默认情况下将选择最后一次访问的文件。 在此操作中您还可以通过左侧列访问任何工具窗口。
- 使用*文件结构*操作查看当前文件的结构。 按 **Control+F12**（在 Mac 上，按 **Command+F12**）调出“文件结构”操作。您可以使用此操作快速导航至当前文件的任何部分。
- 使用*导航至类*操作搜索并导航至项目中的特定类。 按 **Control+N**（在 Mac 上，按 **Command+O**）调出此操作。 “导航至类”支持复杂的表达式，包括驼峰、路径、直线导航和中间名匹配等。 如果连续两次调用此操作，将显示项目类以外的结果。
- 使用*导航至文件*操作导航至文件或文件夹。 按 **Control+Shift+N**（在 Mac 上，按 **Command+Shift+O**）调出“导航至文件”操作。要搜索文件夹，但不搜索文件，请在表达式末尾添加“/”。
- 使用*导航至符号*操作按名称导航至方法或字段。按 **Control+Shift+Alt+N**（在 Mac 上，按 **Command+Shift+Alt+O**）调出“导航至符号”操作。
- 按 **Alt+F7** 查找引用当前光标位置处的类、方法、字段、参数或语句的所有代码片段。

### 样式和格式化

在您编辑时，Android Studio 将自动应用代码样式设置中指定的格式设置和样式。您可以通过编程语言自定义代码样式设置，包括指定选项卡和缩进、空格、换行、花括号以及空白行的约定。要自定义代码样式设置，请点击 **File > Settings > Editor > Code Style**（在 Mac 上，点击 **Android Studio > Preferences > Editor > Code Style**）。

虽然 IDE 会在您工作时自动应用格式化，但您也可以通过按 **Control+Alt+L**（在 Mac 上，按 **Opt+Command+L**）显式调用*重新格式化代码*操作，或按 *Control+Alt+I\**（在 Mac 上，按 **Alt+Option+I**）自动缩进所有行。

![img](https://developer.android.google.cn/studio/images/intro/code-before-formatting_2-1_2x.png)

**图 4.** 格式化前的代码。

![img](https://developer.android.google.cn/studio/images/intro/code-after-formatting_2-1_2x.png)

**图 5.** 格式化后的代码。

### 版本控制基础知识

Android Studio 支持多个版本控制系统 (VCS)，包括 Git、GitHub、CVS、Mercurial、Subversion 和 Google Cloud Source Repositories。

在将您的应用导入 Android Studio 后，使用 Android Studio VCS 菜单选项启用对所需版本控制系统的 VCS 支持、创建存储库、导入新文件至版本控制以及执行其他版本控制操作：

1. 在 Android Studio **VCS** 菜单中点击 **Enable Version Control Integration**。
2. 从下拉菜单中选择要与项目根目录关联的版本控制系统，然后点击 **OK**。

此时，VCS 菜单将根据您选择的系统显示多个版本控制选项。

**注：** 您还可以使用 **File > Settings > Version Control** 菜单选项设置和修改版本控制设置。

## 3. Gradle 构建系统

Android Studio 基于 Gradle 构建系统，并通过 [Android Gradle 插件](https://developer.android.google.cn/tools/revisions/gradle-plugin.html)提供更多面向 Android 的功能。该构建系统可以作为集成工具从 Android Studio 菜单运行，也可从命令行独立运行。您可以利用构建系统的功能执行以下操作：

- 自定义、配置和扩展构建流程。
- 使用相同的项目和模块为您的应用创建多个具有不同功能的 APK。
- 在不同源代码集中重复使用代码和资源。

利用 Gradle 的灵活性，您可以在不修改应用核心源文件的情况下实现以上所有目的。 Android Studio 构建文件以 `build.gradle` 命名。 这些文件是纯文本文件，使用 Android Gradle 插件提供的元素以 [Groovy](http://groovy.codehaus.org/) 语法配置构建。每个项目有一个用于整个项目的顶级构建文件，以及用于各模块的单独的模块层级构建文件。在导入现有项目时，Android Studio 会自动生成必要的构建文件。

如需了解有关构建系统和如何配置的更多信息，请参阅[配置构建](https://developer.android.google.cn/tools/building/plugin-for-gradle.html#build-config)。

### 构建变体

构建系统可帮助您从一个项目创建同一应用的不同版本。 如果您同时拥有免费版本和付费版本的应用，或想要在 Google Play 上为不同设备配置分发多个 APK，则可以使用此功能。

如需了解有关配置构建变体的详细信息，请参阅[配置 Gradle 构建](https://developer.android.google.cn/tools/building/configuring-gradle.html#workBuildVariants)。

### APK 拆分

通过 APK 拆分，您可以高效地基于屏幕密度或 ABI 创建多个 APK。 例如，您可以利用 APK 拆分创建单独的 hdpi 和 mdpi 版本应用，同时仍将它们视为一个变体，并允许其共享测试应用、javac、dx 和 ProGuard 设置。

如需了解有关使用 APK 拆分的详细信息，请参阅 [APK 拆分](http://tools.android.com/tech-docs/new-build-system/user-guide/apk-splits)。

### 资源压缩

Android Studio 中的资源压缩功能可自动从您打包的应用和库依赖关系中删除不使用的资源。 例如，如果您的应用正在使用 [Google Play 服务](https://developer.android.google.cn/google/play-services/index.html)，以访问 Google 云端硬盘功能，且您当前未使用 [Google Sign-In](https://developer.android.google.cn/google/play-services/plus.html)，则资源压缩功能可删除 `SignInButton` 按钮的各种可绘制资产。

**注：** 资源压缩与代码压缩工具（例如 ProGuard）协同工作。

如需了解有关压缩代码和资源的详细信息，请参阅[压缩代码和资源](https://developer.android.google.cn/tools/help/proguard.html)。

### 管理依赖关系

项目的依赖关系在 `build.gradle` 文件中按名称指定。 Gradle 可自动查找您的依赖关系，并在构建中提供。 您可以在 `build.gradle` 文件中声明模块依赖关系、远程二进制依赖关系以及本地二进制依赖关系。 Android Studio 配置项目时默认使用 Maven 中央存储库。 （该配置包含在项目的顶级构建文件中。） 如需了解有关配置依赖关系的详细信息，请参阅[配置构建变体](https://developer.android.google.cn/tools/building/configuring-gradle.html#dependencies)。

## 4. 调试和配置文件工具

Android Studio 可帮助您调试和改进代码的性能，包括内联调试和性能分析工具。

### 内联调试

使用内联调试功能在调试程序视图中对引用、表达式和变量值进行内联验证，提高代码走查效率。内联调试信息包括：

- 内联变量值
- 引用某选定对象的引用对象
- 方法返回值
- Lambda 和运算符表达式
- 工具提示值

![img](https://developer.android.google.cn/studio/images/intro/inline-variable-value-debug_2-1_2x.png)

**图 6.** 内联变量值。

要启用内联调试，请在 **Debug** 窗口中点击 **Settings** ![img](https://developer.android.google.cn/images/tools/studio-debug-settings-icon.png)并选中 **Show Values Inline** 复选框。

### 性能监视器

Android Studio 提供性能监视器，让您可以更加轻松地跟踪应用的内存和 CPU 使用情况、查找已解除内存分配的对象、查找内存泄漏以及优化图形性能和分析网络请求。在设备或模拟器上运行您的应用时，打开 **Android Monitor** 工具窗口，然后点击 **Monitors** 选项卡。

如需了解有关性能监视器的详细信息，请参阅 [Android Monitor](https://developer.android.google.cn/tools/help/android-monitor.html)。

### 堆转储

在 Android Studio 中监控内存使用情况时，您可以同时启动垃圾回收并将 Java 堆转储为 Android 专有 HPROF 二进制格式的堆快照文件。HPROF 查看器显示类、每个类的实例以及引用树，可以帮助您跟踪内存使用情况，查找内存泄漏。

如需了解有关使用堆转储功能的详细信息，请参阅[转储和分析 Java 堆](https://developer.android.google.cn/tools/help/am-memory.html#dumping)。

### 分配跟踪器

Android Studio 允许在监视内存使用情况的同时跟踪内存分配情况。 利用跟踪内存分配功能，您可以在执行某些操作时监视对象被分配到哪些位置。 了解这些分配后，您就可以相应地调整与这些操作相关的方法调用，从而优化应用的性能和内存使用。

如需了解有关跟踪和分析分配的详细信息，请参阅[分配跟踪器](https://developer.android.google.cn/tools/help/am-allocation.html)。

### 数据文件访问

[Systrace](https://developer.android.google.cn/tools/help/systrace.html)、[logcat](https://developer.android.google.cn/tools/help/logcat.html) 和 [Traceview](https://developer.android.google.cn/tools/help/traceview.html) 等 Android SDK 工具可生成性能和调试数据，用于对应用进行详细分析。

要查看已生成的数据文件，请打开“Captures”工具窗口。 在已生成的文件列表中，双击相应的文件即可查看数据。右键点击任何 `.hprof` 文件即可将其转换为标准 [`.hprof`](https://developer.android.google.cn/tools/help/hprof-conv.html) 文件格式。

### 代码检查

在您每次编译程序时，Android Studio 都将自动运行已配置的 [Lint](https://developer.android.google.cn/tools/help/lint.html) 及其他 [IDE 检查](https://www.jetbrains.com/help/idea/2016.1/code-inspections.html?origin=old_help&search=inspection)，以帮助您轻松识别和纠正代码结构质量问题。

Lint 工具可检查您的 Android 项目源文件是否有潜在的错误，以及在正确性、安全性、性能、可用性、无障碍性和国际化方面是否需要优化改进。

![img](https://developer.android.google.cn/studio/images/intro/lint-inspection-results_2-1_2x.png)

**图 7.** Android Studio 中 Lint 检查的结果。

除了 Lint 检查，Android Studio 还可以执行 IntelliJ 代码检查和注解验证，以简化您的编码工作流程。

如需了解详细信息，请参阅[使用 Lint 改进代码](https://developer.android.google.cn/tools/debugging/improving-w-lint.html)和 [lint 工具](https://developer.android.google.cn/tools/help/lint.html)。

### Android Studio 中的注解

Android Studio 支持为变量、参数和返回值添加注解，以帮助您捕捉错误，例如 null 指针异常和资源类型冲突。 Android SDK 管理器将支持注解库纳入 Android 支持存储库中，供与 Android Studio 结合使用。 Android Studio 在代码检查期间验证已配置的注解。

有关 Android 注解的更多详细信息，请参阅[使用注解改进代码检查](https://developer.android.google.cn/tools/debugging/annotations.html)。

### 日志消息

在使用 Android Studio 构建和运行应用时，您可以点击窗口底部的 **Android Monitor** 查看 [adb](https://developer.android.google.cn/tools/help/adb.html) 输出和设备日志消息 ([logcat](https://developer.android.google.cn/tools/help/logcat.html))。

如果您想使用 [Android 设备监视器](https://developer.android.google.cn/tools/help/monitor.html)调试您的应用，您可以点击 **Tools > Android > Android Device Monitor** 启动设备监视器。设备监视器中提供全套的 DDMS 工具，您可以使用这些工具进行应用分析和设备行为控制等操作。此外，该监视器还包括层次结构查看器工具，可帮助您优化布局。