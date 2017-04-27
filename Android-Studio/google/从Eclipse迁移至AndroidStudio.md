将项目迁移至 Android Studio 需要适应新的项目结构、构建系统和 IDE 功能。 为了简化迁移过程，Android Studio 提供了导入工具，您可以将现有代码快速移至 Android Studio 项目和基于 Gradle 的构建文件。

## 1. Android Studio 基础知识

在准备迁移至 Android Studio 时您需要了解以下关键区别。

### 项目和模块组织

Android Studio 基于 [IntelliJ IDEA](https://www.jetbrains.com/idea/) IDE。 如需了解 IDE 基础知识，例如导航、代码自动完成和键盘快捷键，请参阅[探索 Android Studio](https://developer.android.google.cn/studio/intro/index.html)。

Android Studio 不使用工作区，因此各个项目在单独的 Android Studio 窗口中打开。 Android Studio 将代码组织到项目中，其中包含从应用源代码到构建配置和测试代码等定义 Android 应用的所有信息。每个项目包含一个或多个模块，您可以将项目分成独立的功能单元。模块可独立构建、测试和调试。

如需了解有关 Android Studio 项目和模块的详细信息，请参阅[项目概览](https://developer.android.google.cn/tools/projects/index.html)。

### 基于 Gradle 的构建系统

Android Studio 的构建系统基于 [Gradle](http://gradle.org/)，并使用以 Groovy 语法编写的构建配置文件，以便于扩展和自定义。

如需了解有关使用和配置 Gradle 的详细信息，请参阅[配置构建](https://developer.android.google.cn/tools/building/plugin-for-gradle.html)。

### 依赖关系

在 Android Studio 中，库依赖关系使用依赖关系声明，对于具有 Maven 坐标的已知本地源代码和二进制库，则使用 Maven 依赖关系。如需了解详细信息，请参阅[配置构建变体](https://developer.android.google.cn/tools/building/configuring-gradle.html#dependencies)。

### 测试代码

通过使用 Eclipse ADT，可在不同的项目中编写仪器测试，并通过清单文件中的 `<instrumentation>` 元素进行集成。Android Studio 在项目的主源代码集中提供 `androidTest/` 目录，因此您可以在同一项目视图中轻松添加和维护仪器测试代码。 Android Studio 在项目的主源代码集中还提供了 `test/` 目录，用于本地 JVM 测试。

## 2. 迁移先决条件

在将您的应用迁移到 Android Studio 前，请浏览以下步骤，确保您的项目已做好转换的准备，同时确认 Android Studio 中有您需要的工具配置：

### 在 Eclipse ADT 中：

- 确保 Eclipse ADT 根目录包含 `AndroidManifest.xml` 文件。 此外，根目录必须包含 Eclipse 的 `.project` 和 `.classpath` 文件或 `res/` 和 `src/` 目录。
- 构建您的项目，以确保导入时保存并包含了最新的工作区和项目更新。
- 在需要导入的 `project.properties` 或`.classpath` 文件中注释掉对 Eclipse ADT 工作区库文件的任何引用。 您可以在导入后在 `build.gradle` 文件中添加这些引用。 如需了解详细信息，请参阅[配置构建](https://developer.android.google.cn/tools/building/plugin-for-gradle.html)。
- 记录工作区目录、路径变量和任何实际路径映射可能会有所帮助，这些内容可用于指定任何未解析的相对路径、路径变量和链接的资源引用。Android Studio 允许您在导入过程中手动指定任何未解析的路径。

### 在 Android Studio 中：

- 如果您尚未安装，点击此处[下载 Android Studio](https://developer.android.google.cn/studio/index.html)。 如果您已经安装了 Android Studio，请点击 **Help > Check for Updates**（在 Mac 上，点击 **Android Studio > Check for Updates**），验证其是否是最新的稳定版本。
- 因为 Android Studio 无法迁移任何第三方 Eclipse ADT 插件，请记下您在 Eclipse 中使用的任何第三方插件。您可以查看 Android Studio 中的相同功能，或在 [IntelliJ Android Studio 插件](https://plugins.jetbrains.com/?androidstudio)存储库中搜索兼容的插件。使用 **File > Settings > Plugins** 菜单选项管理 Android Studio 中的插件。
- 如果您计划在防火墙后面运行 Android Studio，则必须为 Android Studio 和 SDK 管理器设置代理。 Android Studio 设置向导同步、第三方库访问、访问远程存储库、[Gradle](http://www.gradle.org/) 初始化和同步以及 Android Studio 版本更新需要互联网连接。如需了解详细信息，请参阅[代理设置](https://developer.android.google.cn/tools/studio/studio-config.html#proxy)。

## 3. 将项目导入 Android Studio

您应根据现有 Eclipse ADT 项目的结构确定其导入方式：

- 如果您在 Eclipse ADT 中有多个关联项目共享同一个工作区，请将第一个项目[作为项目](https://developer.android.google.cn/studio/intro/migrate.html#import-project)导入，然后添加随后的关联项目[作为该项目中的模块](https://developer.android.google.cn/studio/intro/migrate.html#import-module)。
- 如果您的 Eclipse ADT 项目在同一个工作区中共享依赖关系，但并不关联，请将每个 Eclipse ADT 项目作为独立的项目逐个导入 Android Studio。在导入过程中 Android Studio 将在新创建的项目之间维持这些共享的依赖关系。

### 作为项目导入：

1. 启动 Android Studio，并关闭任何打开的 Android Studio 项目。

2. 在 Android Studio 菜单中点击 **File > New > Import Project**。或在“Welcome”屏幕中点击 **Import project (Eclipse ADT, Gradle, etc.)**。

3. 选择包含 `AndroidManifest.xml` 文件的 Eclipse ADT 项目文件夹，并点击 **Ok**。![img](https://developer.android.google.cn/studio/images/intro/select-project-to-import_2-1_2x.png)

4. 选择目标文件夹，并点击 **Next**。![img](https://developer.android.google.cn/studio/images/intro/project-destination-folder_2-1_2x.png)

5. 选择导入选项，并点击 **Finish**。

6. 导入过程中会提示您将任何库和项目依赖关系迁移到 Android Studio，并将依赖关系声明添加到 `build.gradle` 文件。如需了解有关此过程的详细信息，请参阅[创建 Android 库](https://developer.android.google.cn/studio/projects/android-library.html)。

   导入过程中还将用 Maven 依赖关系替换具有已知 Maven 坐标的任何已知源代码库、二进制库和 JAR 文件，因此您无需手动保留这些依赖关系。导入选项还允许您输入工作区目录和任何实际路径映射，以处理任何未解析的相对路径、路径变量和链接的资源引用。

![img](https://developer.android.google.cn/studio/images/intro/select-import-options_2-1_2x.png)

1. Android Studio 导入应用并显示项目导入摘要。 查看摘要，了解项目重组和导入过程的详细信息。

![img](https://developer.android.google.cn/studio/images/intro/import-summary_2-1_2x.png)

将项目从 Eclipse ADT 导入 Android Studio 后，Android Studio 中的每个应用模块文件夹都包含该模块的完整源代码集，包括 `src/main/` 和 `src/androidTest/`目录、资源、构建文件以及 Android 清单。在开始应用开发前，您应解决项目导入摘要中显示的所有问题，确保项目重组和导入过程成功完成。

### 作为模块导入：

1. 启动 Android Studio，并打开想要添加模块的项目。
2. 在 Android Studio 菜单中点击 **File > New > Import Module**。
3. 选择包含 `AndroidManifest.xml` 文件的 Eclipse ADT 项目文件夹，并点击 **Ok**。
4. 如果需要，可修改模块名称，并点击 **Next**。
5. 导入过程中会提示您将任何库和项目依赖关系迁移到 Android Studio，并将依赖关系声明添加到 `build.gradle` 文件。如需了解有关迁移库和项目依赖关系的详细信息，请参阅[创建 Android 库](https://developer.android.google.cn/studio/projects/android-library.html)。导入过程中还将用 Maven 依赖关系替换具有已知 Maven 坐标的任何已知源代码库、二进制库和 JAR 文件，因此您无需手动保留这些依赖关系。导入选项还允许您输入工作区目录和任何实际路径映射，以处理任何未解析的相对路径、路径变量和链接的资源引用。
6. 点击 **Finish**。

### 验证导入的项目

完成导入过程后，使用 Android Studio 的 Build 和 Run 菜单选项构建您的项目，并验证输出。若项目未正确构建，请检查以下设置：

- 打开 [SDK 管理器](https://developer.android.google.cn/tools/help/sdk-manager.html#sdk-manager)（点击 Android Studio 中的“Android SDK Manager”按钮或 **Tools > Android > SDK Manager**），验证您安装的工具版本是否匹配 Eclipse 项目的设置。Android Studio 从您导入的 Eclipse 项目继承 SDK 管理器和 JDK 设置。
- 要验证其他 Android Studio 设置，请点击 **File > Project Structure** 并检查以下设置：在 **SDK Location** 项下，验证 Android Studio 是否可以访问正确的 SDK、NDK 和 JDK 位置和版本。在 **Project** 项下，验证 Gradle 版本、Android 插件版本和相关存储库。在 **Modules** 项下，验证应用和模块设置，例如签署配置和库依赖关系。
- 如果您的项目依赖另一个项目，则确保在应用模块文件夹中的 `build.gradle` 文件中正确定义该依赖关系。如需了解有关定义依赖关系的详细信息，请参阅[配置构建变体](https://developer.android.google.cn/tools/building/configuring-gradle.html#dependencies)。

如果在检查这些设置后，在 Android Studio 中构建和运行项目时仍出现异常问题，请考虑修改 Eclipse ADT 项目并重新开始导入过程。

**注：** 将 Eclipse ADT 项目导入 Android Studio 将创建一个新的 Android Studio 项目，不会影响现有 Eclipse ADT 项目。

## 4. 后续步骤

根据您的项目和工作流程，您可能想要阅读更多有关使用版本控制、管理依赖关系、签署和打包应用或配置和更新 Android Studio 的信息。

若要开始使用 Android Studio，请阅读[探索 Android Studio](https://developer.android.google.cn/studio/intro/index.html)。

### 配置版本控制

Android Studio 支持多个版本控制系统，包括 Git、GitHub、CVS、Mercurial、Subversion 和 Google Cloud Source Repositories。

在将您的应用导入 Android Studio 后，使用 Android Studio VCS 菜单选项启用对所需版本控制系统的 VCS 支持、创建存储库、导入新文件至版本控制以及执行其他版本控制操作：

1. 在 Android Studio VCS 菜单中点击 **Enable Version Control Integration**。
2. 从下拉菜单中选择要与项目根目录关联的版本控制系统，然后点击 **OK**。 此时，VCS 菜单将根据您选择的系统显示多个版本控制选项。

**注：** 您还可以使用 **File > Settings > Version Control** 菜单选项设置和修改版本控制设置。

如需了解有关使用版本控制的详细信息，请参阅 [IntelliJ 版本控制参考](https://www.jetbrains.com/help/idea/2016.1/version-control-reference.html?search=version)。

### Android 支持存储库和 Google Play 服务存储库

虽然 Eclipse ADT 使用 Android 支持库和 Google Play 服务库，但在导入过程中 Android Studio 会用 Android 支持存储库和 Google 存储库替换这些库，以便继续使用兼容的功能并支持新的 Android 功能。Android Studio 使用已知的 Maven 坐标将这些依赖关系添加为 Maven 依赖关系，因此不需要手动更新这些依赖关系。

在 Eclipse 中，要使用支持库，您必须针对想要使用的每个支持库在开发环境中修改项目的类路径依赖关系。在 Android Studio 中，无需将库源代码复制到您自己的项目中，您只需声明依赖关系，即可自动下载库并将其合并到您的项目中。 这包括在构建时自动合并到资源、清单条目、ProGuard 排除规则和自定义 Lint 规则。 如需了解有关依赖关系的详细信息，请参阅[配置构建变体](https://developer.android.google.cn/tools/building/configuring-gradle.html#dependencies)。

### 应用签署

如果您的应用在 Eclipse ADT 中使用调试证书，Android Studio 将继续引用该证书。 或者，调试配置使用 Android Studio 生成的一个调试密钥库和一个默认密钥，二者密码均已知，调试密钥库位于 `$HOME/.android/debug.keystore` 中。

当您从 Android Studio 运行或调试您的项目时，调试构建类型将自动使用此调试配置。在构建用于发布的应用时，Android Studio 会应用在 Eclipse ADT 中使用的发布证书。 如果在导入过程中未找到发布证书，则将发布签署配置添加到 `build.gradle` 文件，或使用 **Build > Generate Signed APK** 菜单选项打开 *Generate Signed APK Wizard*。如需了解签署应用的详细信息，请参阅[签署您的应用](https://developer.android.google.cn/tools/publishing/app-signing.html#studio)。

### 调整 Android Studio 的最大堆内存

默认情况下，Android Studio 的最大堆内存为 1280MB。 如果您要处理较大的项目，或您的系统有大量 RAM 可用，您可以通过在 Android Studio 的 VM 选项中增加最大堆内存来提高性能。

如需了解有关配置 Android Studio 设置的详细信息，请参阅[配置 Android Studio](https://developer.android.google.cn/tools/studio/studio-config.html) 和[配置 Android Studio](http://tools.android.com/tech-docs/configuration)。

### 软件更新

Android Studio 与 Gradle 插件、构建工具和 SDK 工具分开更新。 您可以指定想要使用的 Android Studio 版本。

默认情况下，在有新稳定版本发布时 Android Studio 将自动更新，但您可以选择更频繁地进行更新，也可以接收预览版或测试版。

如需了解有关更新 Android Studio 以及使用预览版和测试版的详细信息，请参阅[保持更新](https://developer.android.google.cn/tools/help/sdk-manager.html)。