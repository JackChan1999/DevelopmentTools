Android Studio 提供诸多向导和模板，可用于验证系统要求（例如 Java 开发工具包 (JDK) 和可用内存）和配置默认设置（例如优化的默认 Android Virtual Device (AVD) 模拟和更新的系统映像）。本文件介绍了您可能想要使用的其他配置设置，以便您自定义对 Android Studio 的使用方式。

有关模拟器和设备设置与使用的特定文档，请参阅[管理虚拟设备](https://developer.android.google.cn/tools/devices/index.html)、[使用硬件设备](https://developer.android.google.cn/tools/device.html)和 [OEM USB 驱动程序](https://developer.android.google.cn/tools/extras/oem-usb.html)。

## 代理设置

代理作为 HTTP 客户端和 Web 服务器之间的中间连接点，可提高互联网连接的安全性和隐私性。

要支持在防火墙后面运行 Android Studio，需要为 Android Studio IDE 和 SDK 管理器设置代理。使用 Android Studio IDE HTTP 代理设置页面设置 Android Studio 的 HTTP 代理。SDK 管理器有单独的 HTTP 代理设置页面。

若从命令行或在未安装 Android Studio 的设备（例如持续性集成服务器）上运行 Android Gradle 插件，则应在 Gradle 构建文件中设置代理。

**注**：在初始安装 Android Studio 程序包后，可以通过互联网访问或脱机运行 Android Studio。但是，Android Studio 设置向导同步、第三方库访问、访问远程存储库、Gradle 初始化和同步以及 Android Studio 版本更新需要互联网连接。

### 设置 Android Studio 代理

Android Studio 支持 HTTP 代理设置，因此您可以在防火墙后面或使用安全网络运行 Android Studio。要在 Android Studio 中设置 HTTP 代理，请执行以下操作：

1. 在主菜单中选择 **File > Settings > Appearance & Behavior -- System Settings -- HTTP Proxy**。

2. 在 Android Studio 中，打开“IDE Settings”对话框。

   - 在 Windows 和 Linux 系统中，选择 **File > Settings > IDE Setting -- HTTP Proxy**。
   - 在 Mac 系统中，选择 **Android Studio > Preferences > IDE Setting -- HTTP Proxy**。

   此时将出现 HTTP Proxy 页面。

3. 选择 **auto-detection** 使用自动配置 URL 配置代理设置，或选择 **manual** 手动输入每一项设置。有关这些设置的详细说明，请参阅 [HTTP 代理](https://www.jetbrains.com/idea/help/http-proxy.html)。

4. 点击 **Apply** 以启用代理设置。

### Android Gradle 插件 HTTP 代理设置

若从命令行或在未安装 Android Studio 的设备上运行 Android 插件，则应在 Gradle 构建文件中设置 Android Gradle 插件代理。

对于应用程序特定的 HTTP 代理设置，请根据各应用程序模块的要求在 `build.gradle` 文件中设置代理。

```
apply plugin: 'com.android.application'

android {
    ...

    defaultConfig {
        ...
        systemProp.http.proxyHost=proxy.company.com
        systemProp.http.proxyPort=443
        systemProp.http.proxyUser=userid
        systemProp.http.proxyPassword=password
        systemProp.http.auth.ntlm.domain=domain
    }
    ...
}
```

对于整个项目的 HTTP 代理设置，应在 `gradle/gradle.properties` 文件中设置代理。

```
# Project-wide Gradle settings.
...

systemProp.http.proxyHost=proxy.company.com
systemProp.http.proxyPort=443
systemProp.http.proxyUser=username
systemProp.http.proxyPassword=password
systemProp.http.auth.ntlm.domain=domain

systemProp.https.proxyHost=proxy.company.com
systemProp.https.proxyPort=443
systemProp.https.proxyUser=username
systemProp.https.proxyPassword=password
systemProp.https.auth.ntlm.domain=domain

...
```

有关使用 Gradle 属性进行代理设置的信息，请参阅 [Gradle 用户指南](http://www.gradle.org/docs/current/userguide/build_environment.html)。

**注**：在使用 Android Studio 时，Android Studio IDE HTTP 代理设置页面中的设置将重写 **gradle.properties** 文件中的 HTTP 代理设置。

### SDK 管理器 HTTP 代理设置

SDK 管理器代理设置可启用代理互联网访问，以便从 SDK 管理器软件包进行 Android 软件包和库更新。

要设置 SDK 管理器的代理互联网访问，请启动 SDK 管理器并打开 SDK 管理器页面。

- 在 Windows 系统中，从菜单栏选择 **Tools > Options**。
- 在 Mac 和 Linux 系统中，从系统菜单栏选择 **Tools > Options**。

此时出现 Android SDK Manager 页面。输入设置并点击 **Apply**。