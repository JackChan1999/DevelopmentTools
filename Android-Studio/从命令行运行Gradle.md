## 本文内容

1. [在调试模式下构建](https://developer.android.google.cn/studio/build/building-cmdline.html#DebugMode)
2. [在发布模式下构建](https://developer.android.google.cn/studio/build/building-cmdline.html#ReleaseMode)[构建未签署应用](https://developer.android.google.cn/studio/build/building-cmdline.html#ManualReleaseMode)[构建已签署并优化的应用](https://developer.android.google.cn/studio/build/building-cmdline.html#AutoReleaseMode)[在发布模式下构建并签署后](https://developer.android.google.cn/studio/build/building-cmdline.html#OnceBuilt)
3. [在模拟器上运行您的应用](https://developer.android.google.cn/studio/build/building-cmdline.html#RunningOnEmulator)
4. [在设备上运行您的应用](https://developer.android.google.cn/studio/build/building-cmdline.html#RunningOnDevice)
5. [应用签署](https://developer.android.google.cn/studio/build/building-cmdline.html#Signing)
6. [插件语言参考](https://developer.android.google.cn/studio/build/building-cmdline.html#PluginReference)

## 另请参阅

1. [构建系统](https://developer.android.google.cn/studio/build/index.html)
2. [使用 Android Emulator](https://developer.android.google.cn/tools/devices/emulator.html)
3. [签署您的应用](https://developer.android.google.cn/tools/publishing/app-signing.html)

默认情况下，使用 Gradle 构建设置构建您的应用有两种构建类型：一种类型用于调试您的应用（*调试模式*），一种类型用于构建最终用于发布的软件包（*发布模式*）。无论您的模块使用哪一种构建类型，应用必须经过签署，才能安装在模拟器或设备上——在调试模式下构建时使用调试密钥签署；在发布模式下构建时使用您自己的私钥签署。

无论您是使用调试还是发布构建类型进行构建，都需要运行并构建您的模块。此操作将创建可供您安装在模拟器或设备上的 .apk 文件。当您使用调试构建类型进行构建时，SDK 工具会根据模块 build.gradle 文件中的 `debuggable true` 设置使用调试密钥自动签署 .apk 文件，以便能够立即安装到模拟器或相连的开发设备上。您无法分发使用调试密钥签署的应用。当您使用发布构建类型进行构建时，.apk 文件处于*未签署*状态，因此您必须按照模块 `build.gradle` 文件中的 Keytool 和 Jarsigner 设置用您自己的私钥手动签署该文件。

您必须阅读并理解[签署您的应用](https://developer.android.google.cn/tools/publishing/app-signing.html)，尤其是在您已准备好发布应用并将其分享给最终用户的时候。该文档描述了生成私钥以及随后使用它来签署 APK 文件的程序。不过，如果您只是刚刚入门，可以在调试模式下构建，这样就能在模拟器或您自己的开发设备上快速运行您的应用。

如果您没有 [Gradle](http://www.gradle.org/)，可以从 [Gradle 主页](http://gradle.org/)获取。安装 Gradle 并确保它位于您的可执行文件 PATH 内。在调用 Gradle 前，您需要声明 JAVA_HOME 环境变量，将路径指定为 JDK 的安装位置。

**注**：在 Windows 上使用 `ant` 和安装 JDK 时，默认安装位置是“Program Files”目录。由于存在空格，该位置会导致 `ant` 失败。要修正该问题，您可以像下面这样指定 JAVA_HOME 变量：

```
set JAVA_HOME=c:\Progra~1\Java\<jdkdir>
```

不过，最容易的解决方案是将 JDK 安装在一个不含空格的目录中，例如：

```
c:\java\jdk1.7
```

您还应将项目设置为使用 [Gradle 包装器](https://docs.gradle.org/current/userguide/gradle_wrapper.html)，他人可以利用这个工具在一致的环境中构建您的项目。Gradle 包装器提供了适用于 Windows 的批处理文件，以及适用于 Linux 和 Mac OSX 的 shell 脚本，它们会自动下载和使用您为项目指定的 Gradle 版本。这样一来，您就可以通过包装器对项目运行 Gradle 任务，而不必考虑与其他构建系统版本的兼容性问题。

**注**：如果您使用 Android Studio 创建新项目，IDE 会自动为您设置 Gradle 包装器，这样您就无需执行这些设置说明。

要为您的项目指定 Gradle 版本并初始化 Gradle 包装器，请从项目的根目录运行以下命令：

```
gradle wrapper --gradle-version version-number

```

Gradle 执行包装器任务并生成下列文件：

- `./gradlew.bat` 和 `./gradlew`：分别是包装器的批处理文件和 shell 脚本文件。
- `./gradle/wrapper/gradle-wrapper.jar`：批处理文件和 shell 脚本文件使用的 JAR 文件。
- `./gradle/wrapper/gradle-wrapper.properties`：包括包装器配置（例如分发网址和您为项目指定的 Gradle 版本）的属性文件。

**注**：您应该将以上所列文件加入到版本控制系统内。这样一来，任何使用您的项目的人员将同时获得重现您的构建所需的包装器文件和配置。

您现在可以使用 Gradle 包装器对您的项目运行 Gradle 任务——包装器会自动将任务委派给正确的 Gradle 版本。要使用包装器运行任务，请使用下列命令之一：

- 在 Windows 上：`gradlew.bat task-name`
- 在 Mac OSX 或 Linux 上：`./gradlew task-name`

## 在调试模式下构建

------

为了能够立即进行应用测试和调试，您可以在调试模式下构建应用，然后立即将其安装在模拟器上。在调试模式下，构建工具会自动使用调试密钥签署您的应用，并使用 `zipalign` 优化软件包。

要在调试模式下进行构建，请打开命令行并导航至项目目录的根目录。在调试模式下使用 Gradle 构建项目，使用 Gradle 包装器脚本 (`gradlew assembleRelease`) 调用 `assembleDebug` 构建任务。

此操作将在模块 `build/` 目录内创建一个名为 `<your_module_name>-debug.apk` 的 `.apk` 调试文件。该文件已使用调试密钥签署，并且已使用 [`zipalign`](https://developer.android.google.cn/tools/help/zipalign.html) 进行了优化。

在 Windows 平台上，键入以下命令：

```
> gradlew.bat assembleDebug
```

在 Mac OS 和 Linux 平台上，键入以下命令：

```
$ chmod +x gradlew
$ ./gradlew assembleDebug
```

第一个命令 (`chmod`) 用于向 Gradle 包装器脚本添加执行权限，只有在您首次从命令行构建此项目时才需要此命令。

构建项目后，应用模块的输出 APK 位于 `app/build/outputs/apk/` 中，任何内容库模块的输出 AAR 都位于 `lib/build/outputs/libs/` 中。

要查看您的项目所有可用构建任务的列表，请键入以下命令：

```
$ ./gradlew tasks
```

您每次更改源文件或资源时，都必须再次运行 Gradle，以打包最新版本的应用。

要在模拟器上安装并运行您的应用，请参阅[在模拟器上运行您的应用](https://developer.android.google.cn/tools/building/building-studio.html)一节。

## 在发布模式下构建

------

如果您准备发布应用并将其分发给最终用户，则必须在发布模式下构建应用。在发布模式下构建应用后，最好对最终 .apk 执行附加测试和调试。

请注意，在您开始在发布模式下构建应用之前，您必须用自己的私钥签署生成的应用软件包，并且随后还应使用 `zipalign` 工具对其进行优化。发布模式下的构建方法有两种：在发布模式下构建未签署软件包，然后手动签署并优化软件包；或者让构建脚本为您签署和优化软件包。

### 构建未签署应用

如果您构建*未签署*应用，则需手动签署和优化软件包。

要在发布模式下构建*未签署* .apk，请打开命令行并导航至模块目录的根目录。调用 `assembleRelease` 构建任务。

在 Windows 平台上，键入以下命令：

```
> gradlew.bat assembleRelease
```

在 Mac OS 和 Linux 平台上，键入以下命令：

```
$ ./gradlew assembleRelease
```

此操作将在项目 `bin/` 目录内创建一个名为 `*<your_module_name>*-unsigned.apk` 的 .apk Android 应用文件。

**注**：这个 .apk 文件此时处于*未签署*状态，使用您的私钥签署后才能安装。

您创建未签署 .apk 后，下一步是使用您的私钥签署 .apk，然后使用 `zipalign` 对其进行优化。要完成此程序，请阅读[签署您的应用](https://developer.android.google.cn/tools/publishing/app-signing.html)。

签署并优化您的 `.apk` 后，便可将其分发给最终用户。您应该在不同的设备或 AVD 上测试最终构建，以确保它能在不同平台上正常运行。

### 构建已签署并优化的应用

如果您愿意，可以配置相应的 Android 构建脚本来自动签署和优化您的应用软件包。为此，您必须在模块的 build.gradle 文件中提供密钥库的路径以及密钥别名的名称。提供这些信息后，当您使用发布构建类型进行构建时，构建将提示您提供密钥库和别名密码，并生成可随时分发的最终应用软件包。

要指定您的密钥库和别名，请打开模块 build.gradle 文件（位于模块目录的根目录中）并添加 `storeFile`、`storePassword`、`keyAlias` 和 `keyPassword` 条目。例如：

```
storeFile file("myreleasekey.keystore")
keyAlias "MyReleaseKey"
```

保存您的更改。现在您便可在发布模式下构建*已签署* .apk：

1. 打开命令行并导航至模块目录的根目录。

2. 编辑 build.gradle 文件以在发布模式下构建您的项目：

   ​

   ```
   ...
   android {
       ...
       defaultConfig { ... }
       signingConfigs {
           release {
               storeFile file("myreleasekey.keystore")
               storePassword "password"
               keyAlias "MyReleaseKey"
               keyPassword "password"
           }
       }
       buildTypes {
           release {
               ...
               signingConfig signingConfigs.release
           }
       }
   }
   ...
   ```

   ​

3. 出现提示时，输入您的密钥库和别名密码。

   **注意**：如上所述，您的密码将显示在屏幕上。

此操作将在模块 `build/` 目录内创建一个名为 `*<your_module_name>*-release.apk` 的 .apk Android 应用文件。这个 .apk 文件已经使用 build.gradle 文件中指定的私钥签署，并使用 `zipalign` 进行了优化。它可随时进行安装和分发。

### 在发布模式下构建并签署后

使用私钥签署您的应用后，就可以在[模拟器](https://developer.android.google.cn/studio/build/building-cmdline.html#RunningOnEmulator)或[设备](https://developer.android.google.cn/studio/build/building-cmdline.html#RunningOnDevice)上安装并运行应用。您还可以尝试通过网络服务器将其安装到设备上。只需将已签署 .apk 上传至网站，然后在您的 Android 网络浏览器中加载 .apk 网址，便可下载应用并开始安装。（在您的设备上，请确保您已启用 *Settings > Applications > Unknown sources*。）

## 在模拟器上运行您的应用

------

您必须先[创建 AVD](https://developer.android.google.cn/tools/devices/managing-avds.html)，才能在 Android Emulator 上运行您的应用。

要运行您的应用，请执行以下操作：

1. **打开 AVD Manager 并启动一个虚拟设备**在 *Virtual Devices* 视图中，选择一个 AVD 并点击 **Start**。
2. **安装您的应用**从 SDK 的`tools/` 目录中，将 `.apk` 安装在模拟器上：`adb install *<path_to_your_bin>*.apk`构建应用后，您的 .apk 文件（已使用发布或调试密钥签署）位于模块的 `build/` 目录中。如果运行中的模拟器不止一个，您必须使用 `-s` 选项通过序列号指定作为应用安装目的地的模拟器。例如：`adb -s emulator-5554 install *path/to/your/app*.apk`要查看可用设备序列号的列表，请执行 `adb devices`。

如果您在模拟器上未看到您的应用，请尝试关闭模拟器，然后通过 AVD Manager 再次启动虚拟设备。当您首次安装一款应用时，有时它不会出现在应用启动器中，也无法被其他应用访问。这是因为，软件包管理器通常只会在模拟器启动时对清单进行完整检查。

请务必创建多个 AVD 来测试您的应用。您应该为应用兼容的每个平台和屏幕类型分别创建一个 AVD。例如，如果您的应用的编译目标是 Android 4.0（API 级别 14）平台，就应该为每个版本号大于和等于 4.0 的平台创建一个 AVD，并为您支持的每个[屏幕类型](https://developer.android.google.cn/guide/practices/screens_support.html)创建一个 AVD，然后在每个 AVD 上测试您的应用。

**提示**：如果运行中的模拟器*只有一个*，您只需通过一个简单的步骤便可构建您的应用并将它安装在模拟器上。导航至项目目录的根目录，然后使用 Ant 在*安装模式*下编译项目：`ant install`。此操作将构建您的应用，使用调试密钥签署应用，然后将其安装在当前运行的模拟器上。

## 在设备上运行您的应用

------

您必须先为设备执行一些基本的设置，才能在设备上运行您的应用：

- 在您的设备上启用 **USB debugging**。您可以在 **Settings > Developer options** 中找到该选项。**注**：在运行 Android 4.2 及更新版本的设备上，**Developer options** 默认情况下处于隐藏状态。如需将其显示出来，请转到 **Settings > About phone** 并点按 **Build number** 七次。返回上一屏幕即可找到 **Developer options**。
- 通过 USB 连接时，确保您的开发计算机可检测到您的设备

如需了解详细信息，请阅读[面向开发设置设备](https://developer.android.google.cn/tools/device.html#setting-up)。

您的设备设置完毕并通过 USB 连接后，导航至您的 SDK 的 `platform-tools/` 目录并将 `.apk` 安装在设备上：

```
adb -d install path/to/your/app.apk
```

`-d` 标志指定您想使用连接的设备（如果您还有一个运行中的模拟器）。

如需了解有关以上使用的工具的详细信息，请参阅下列文档：

- [Android Emulator](https://developer.android.google.cn/tools/devices/emulator.html)
- [Android 调试桥](https://developer.android.google.cn/tools/help/adb.html) (ADB)

## 应用签署

------

在您着手开发 Android 应用时需要了解的是，所有 Android 应用都必须进行数字签署，系统才能将它们安装在模拟器或设备上。签署的方式有两种：使用*调试密钥*（用于立即在模拟器或开发设备上进行测试），或使用*私钥*（用于进行应用分发）。

Android 构建工具可帮助您入门，它们会在构建时自动使用调试密钥签署您的 .apk 文件。这意味着您在构建应用后不必生成自己的私钥便可将其安装在模拟器上。但请注意，如果您打算发布应用，就**必须**使用自己的私钥签署应用，而不能使用 SDK 工具生成的调试密钥签署应用。

请阅读[签署您的应用](https://developer.android.google.cn/tools/publishing/app-signing.html)，它全面介绍了 Android 上的应用签署及其对作为 Android 应用开发者的您的意义。该文档还提供了对发布和签署应用的指导。

## Android Plugin for Gradle

------

Android 构建系统使用 Android Plugin for Gradle 来支持 Gradle 域特定语言 (DSL) 和声明性语言元素。如需了解对该插件的说明以及支持的 Gradle DSL 元素的完整列表，请参阅 [Android Plug-in for Gradle](https://developer.android.google.cn/tools/building/plugin-for-gradle.html) 部分。