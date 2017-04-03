## 构建 Android 应用之必备功能

Android Studio 是 Android 的官方 IDE。它是专为 Android 而打造，可以加快您的开发速度，帮助您为每款 Android 设备构建最优应用。

它提供专为 Android 开发者量身定制的工具，其中包括丰富的代码编辑、调试、测试和性能分析工具。

![img](https://developer.android.google.cn/images/tools/studio/studio-feature-devices_2x.png)

## 1. 比以往更快的编码和循环访问速度

Android Studio 是基于 Intellij IDEA 而构建，可以提供尽可能最短的编码和运行工作流周转时间。

#### Instant Run

点击“Run”或“Debug”时，Android Studio 的 Instant Run 功能即会将代码和资源更改推送至正在运行的应用。它可以智能地理解这些更改，并且通常无需您重启应用或重新构建 APK 即可传递它们，让您能够即时看到更改效果。

#### 智能代码编辑器

智能代码编辑器提供高级代码自动完成、重构和代码分析功能，可帮助您编写更好的代码，加快您的工作速度，提高您的工作效率。Android Studio 会在您键入时以下拉列表形式提供建议。只需按 Tab 即可插入代码。

#### 快速且功能丰富的模拟器

Android Emulator 可以比实际设备更快的速度安装和启动您的应用，允许您在所有 Android 设备配置（手机、平板电脑、Android Wear 和 Android TV 设备）上对您的应用进行原型设计和测试。此外，您还可以模拟各种硬件功能，例如 GPS 位置、网络延迟和多点触控输入。

## 2. 无限制配置构建

Android Studio 的项目结构和基于 Gradle 的构建工具让您可以根据自己的需要灵活地生成所有设备类型的 APK。

#### 强大灵活的构建系统

Android Studio 提供自动构建、依赖项管理和可自定义的构建配置功能。您可以将项目配置为包含本地库和托管库，定义包含不同代码和资源的构建变体，并应用不同的代码收缩和应用签名配置。

#### 专为团队而设计

Android Studio 集成有诸多版本控制工具，例如 GitHub 和 Subversion，让您的团队能够与项目和构建变更保持同步。利用开源 Gradle 构建系统，您可以根据自己的环境量身定制构建，并在一台持续性集成服务器（如 Jenkins）上运行构建。

#### 专为所有 Android 设备而开发

Android Studio 提供了统一的环境，您可在其中开发适用于 Android 手机、平板电脑、Android Wear、Android TV 以及 Android Auto 的应用。您可以利用结构化代码模块将项目细分成可独立构建、测试和调试的若干功能单元。

## 3. 满怀自信地编码

Android Studio 可以帮助确保您每一步创建的都是最佳代码。

#### 代码模板和示例应用

Android Studio 包含项目和代码模板，可以轻松添加既定模式，例如抽屉式导航栏和分页浏览器。您还可以直接通过“Create Project”屏幕从 GitHub 导入功能全面的应用。您可以试用并重复使用这些由 Google 及其他开发者构建的应用。

#### Lintelligence

Android Studio 提供一个稳健的静态分析框架，并且包含适用于您整个应用的 280 多项不同的 lint 检查。此外，它还提供多种快速修复功能，只需点击一下，即可帮助您解决各类问题，例如性能、安全性和正确性等问题。

#### 测试工具和框架

Android Studio 提供丰富多样的工具和框架，可帮助您测试您的 Android 应用。为您的应用快速构建并运行测试代码，包括 JUnit 4 和功能性 UI 测试。您可以在设备、模拟器、持续性集成环境或 Firebase Test Lab 运行测试。

## 4. 创建丰富且关联的应用

Android Studio 知道，并非所有代码都是使用 Java 语言编写，也并非所有代码都是在用户设备上运行。

#### C++ 和 NDK 支持

Android Studio 允许将 C++ 及 Android NDK 和您的 Java 代码结合使用。它针对 C++ 提供语法突出显示和重构功能，并提供一个基于 lldb 的调试程序，让您可以同时调试 Java 和 C++。

#### 云端集成

通过适用于 Google 云端平台的内置功能，您可以使用 Google 云端点和 Firebase 云消息传递等服务为自己的 Android 应用创建和部署一个后端。

## 5. 消除厌烦的任务

Android Studio 提供诸多 GUI 工具，可以简化应用开发过程中不太有趣的部分。

#### Vector Asset Studio

利用 Android Studio，可以轻松针对每种密度大小创建新的图像资产。利用 Vector Asset Studio，您可以从 Google 提供的 Material Design 图标中进行选择，也可以加载自己的 SVG 文件。然后，Vector Asset Studio 会针对每种屏幕密度生成相应的位图文件，以为不支持 Android 矢量图片格式的较早版本的 Android 系统提供支持。

#### Translations Editor

Translations Editor 为您提供一个容纳所有已翻译资源的单一视图，您可以从中轻松更改或添加译文，以及查找缺失的译文，而无需打开 strings.xml 文件的每个版本。它甚至还提供指向较早翻译服务的链接。