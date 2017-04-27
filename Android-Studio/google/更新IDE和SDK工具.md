安装 Android Studio 后，您可以通过自动更新和 Android SDK 管理器轻松更新 Android Studio IDE 和 Android SDK 工具。

## 更新 IDE 和变更渠道

若有可用的 IDE 更新，Android Studio 将通过小气泡对话框通知您，您也可以点击 **Help** > **Check for Update**（在 Mac 中，点击 **Android Studio** > **Check for Updates**）手动检查更新。

您可以通过以下发布渠道获取 Android Studio 更新：

- **Canary 版渠道**：此渠道发布前沿版本，大约每周更新一次。虽然这些版本存在较多的错误，但已经过测试，我们希望为您提供抢先体验的机会，以便您尝试新功能和提供反馈。此渠道**不推荐用于生产开发**。
- **开发版渠道**：此渠道发布已通过所有内部测试的精选 Canary 版本。
- **测试版渠道**：此渠道发布基于稳定的 Canary 版本的候选版本，以便在进入稳定版渠道前获得反馈。
- **稳定版渠道**：官方稳定版本，可在 [developer.android.com/studio](https://developer.android.google.cn/studio/) 下载。

默认情况下，Android Studio 从稳定版渠道提供更新。如果您想要尝试其他版本的 Android Studio（统称为预览版渠道），您可以选择从其中一个渠道接收更新。

如需变更更新渠道，请执行以下操作：

1. 点击 **File > Settings**（在 Mac 中，点击 **Android Studio > Preferences**），打开 **Preferences** 窗口。
2. 在左侧面板中，点击 **Appearance & Behavior > System Settings > Updates**。
3. 确保已选中 **Automatically check for updates**，然后从下拉列表中选择一个渠道（见图 1）。
4. 点击 **Apply** 或 **OK**。

**图 1.**Android Studio 更新首选项

如果您想要在生产 Android 项目中仍然使用稳定版本的同时试用预览版渠道（Canary、开发或测试版），您可以从 [tools.android.com](http://tools.android.com/download/studio) 下载相应的预览版本，安全地安装另一个版本的 Android Studio。

## 使用 SDK 管理器更新您的工具

Android SDK 管理器提供 SDK 工具、平台和开发应用所需的其他组件。

要打开 SDK 管理器，请点击 **Tools > Android > SDK Manager** 或点击工具栏中的 **SDK Manager** ![img](https://developer.android.google.cn/studio/images/buttons/toolbar-sdk-manager.png)。

已安装的软件包如有更新，其旁边的复选框中会显示短划线 ![img](https://developer.android.google.cn/studio/images/sdk-manager-icon-update_2-0_2x.png)。

- 要更新项目或安装新项目，请点击复选框，其将显示钩形符号。
- 如需卸载软件包，请点击以清除复选框。

待下载的更新在左侧列中以下载图标 ![img](https://developer.android.google.cn/images/tools/studio-sdk-dwnld-icon.png) 表示。待执行的删除以红十字 ![img](https://developer.android.google.cn/images/tools/studio-sdk-removal-icon.png) 表示。

要更新所选的软件包，请点击 **Apply** 或 **OK**，然后同意所有许可协议。

**图 2.**Android SDK 管理器

### 推荐的软件包

您应特别考虑 **SDK Tools** 选项卡中的以下工具：

- **Android SDK 构建工具**

  **必备。**包含构建 Android 应用的工具。请参阅 [SDK 构建工具发行说明](https://developer.android.google.cn/studio/releases/build-tools.html)。

- **Android SDK 平台工具**

  **必备。**包含 Android 平台所需的各种工具，包括 [adb](https://developer.android.google.cn/studio/command-line/adb.html) 工具。

- **Android SDK 工具**

  **必备。**包含基本工具，例如 Android Emulator 和 ProGuard。请参阅 [SDK 工具发行说明](https://developer.android.google.cn/studio/releases/sdk-tools.html)。

- **Android 支持存储库**

  推荐。包含支持库的本地 Maven 存储库，该存储库提供了一组丰富的 API，这些 API 兼容大多数版本的 Android。该工具是 [Android Wear](https://developer.android.google.cn/wear/index.html)、[Android TV](https://developer.android.google.cn/tv/index.html) 和 [Google Cast](https://developers.google.cn/cast/) 等产品的必备工具。如需了解详细信息，请阅读[支持库](https://developer.android.google.cn/topic/libraries/support-library/index.html)。

- **Google 存储库**

  推荐。包含 Google 库的本地 Maven 存储库，该存储库可为您的应用提供各种功能和服务，包括 [Firebase](https://firebase.google.cn/)、[Google 地图](https://developers.google.cn/maps/documentation/android-api/)、[游戏成就和排行榜](https://developers.google.cn/games/services/)等。

在 **SDK Platforms** 选项卡中，您还必须安装至少一个版本的 Android 平台。每个版本均提供多种不同的软件包。如需仅下载所需版本，请点击版本名称旁的复选框。

要查看各 Android 平台所有可用的软件包，请点击窗口底部的 **Show Package Details**。各版本的平台中均提供以下软件包：

**Android SDK 平台**

**必备。**您的开发环境中必须*至少有一个平台*，您方可编译应用。为了在最新设备上提供最佳用户体验，请使用最新版本的平台作为构建目标。您的应用仍然可以在旧版系统上运行，但您必须以最新版本为目标构建应用，以便在安装最新版本 Android 的设备上运行应用时能够使用新功能。

**Intel** 或 **ARM 系统映像**

推荐。运行 [Android Emulator](https://developer.android.google.cn/tools/devices/emulator.html) 需要系统映像。每个版本的平台均包含受支持的系统映像。您也可以在稍后从 [AVD Manager](https://developer.android.google.cn/studio/run/managing-avds.html) 创建 Android Virtual Device (AVD) 时下载系统映像。根据开发计算机的处理器选择 Intel 或 ARM。**注**：如果您计划使用 [Google Play 服务](https://developers.google.cn/android/)的 API，则必须使用 Google API 系统映像。

以上列表并不详尽，您可以[添加其他网站](https://developer.android.google.cn/studio/intro/update.html#AddingSites)，以便从第三方网站下载更多软件包。

在某些情况下，SDK 软件包可能需要另一个工具的特定最低修订版。如果存在这种情况，SDK 管理器将发出警告通知您，并将依赖项添加到您的下载列表。

**提示**：您还可以自定义 `build.gradle` 文件，使每个项目均使用特定的构建链和编译选项。如需了解详细信息，请参阅[配置 Gradle 构建](https://developer.android.google.cn/tools/building/configuring-gradle.html)。

### 编辑或添加 SDK 工具网站

要管理 Android Studio 检查 Android 工具和第三方工具更新的 SDK 网站，请点击 **SDK Update Sites** 选项卡。您可以添加其他提供自有工具的网站，然后从这些网站下载软件包。

例如，某个移动运营商或设备制造商可能会为其自有基于 Android 系统的设备提供额外的 API 库。要使用他们的库开发应用，您可以在 **SDK Update Sites** 选项卡中将其 SDK 工具 URL 添加到 SDK 管理器，以安装他们的 Android SDK 软件包。

如果运营商或设备制造商在其网站上提供了 SDK 加载项存储库文件，请按照下列步骤将其网站添加到 Android SDK 管理器：

1. 点击 **SDK Update Sites** 选项卡。
2. 点击窗口底部的 **Add** ![img](https://developer.android.google.cn/studio/images/buttons/ic_plus.png)。
3. 输入第三方网站的名称和 URL，然后点击 **OK**。
4. 确保已选中 **Enabled** 列中相应的复选框。
5. 点击 **Apply** 或 **OK**。

该网站提供的所有 SDK 软件包都将视情况显示在 **SDK Platforms** 或 **SDK Tools** 选项卡中。