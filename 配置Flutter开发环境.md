# 配置 Flutter 开发环境

> **写在前面：**
>
> 本文档面向天外天移动组新生，主要介绍在 **Windows** 系统下配置 Flutter Android 开发环境的方法。  
> macOS / Linux 用户可参考 Flutter 官方文档进行配置。
>
> 当前微北洋项目使用 **Flutter 3.44**，建议使用相同版本，避免因 Flutter 版本不同产生兼容性问题。

---

## 一、安装 Git

Git 是一个版本控制工具，之后我们会使用 Git 获取、管理和提交项目代码。

### 1. 下载 Git

访问官方下载地址，下载最新版本：

```text
https://git-scm.com/download/win
```

下载安装程序后运行即可。对于第一次使用 Git 的同学，安装选项保持默认即可。

### 2. 检查是否安装成功

安装完成后，打开 `PowerShell`，执行：

```powershell
git --version
```

如果能够看到类似下方的提示，说明 Git 安装成功：

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_1_2026-09-15_16-14-34.jpg)

---

## 二、安装 Flutter SDK

Flutter SDK 包含 Flutter 开发所需的工具，同时也自带 Dart SDK。

### 1. 下载 Flutter

Flutter 官方历史版本页面：

```text
https://docs.flutter.dev/install/archive
```

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_2_2026-09-15_16-14-34.jpg)

如果官方源在中国大陆网络环境下下载较慢，可以使用国内镜像。

南京大学 Flutter 镜像：

```text
https://mirror.nju.edu.cn/flutter/flutter_infra_release/releases/stable/windows/
```

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_3_2026-09-15_16-14-34.jpg)

下载相应的`.zip`压缩包即可

### 2. 解压 Flutter SDK

下载完成后，将压缩包解压到固定位置。建议使用较短的路径，且尽量避免中文和特殊字符。请结合自身情况选择路径，教程此处选择了C盘。

在后续进行版本管理时可以选择`fvm`进行`flutter`版本管理，或在磁盘根目录下建立`flutter`文件夹用来存放不同版本的`flutter sdk`，在项目中手动配置相应路径。

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_4_2026-09-15_16-14-34.jpg)

解压后，复制`flutter/bin`文件夹的路径备用

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_5_2026-09-15_16-14-34.jpg)

---

### 3. 配置 Flutter 环境变量

打开环境变量设置，搜索`环境变量`或`env`  

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_7_2026-09-15_16-14-34.jpg)

回车进入，选择`环境变量`选项

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_8_2026-09-15_16-14-34.jpg)

以下内容建议添加在 **用户变量** 中。

#### 配置 Flutter 国内镜像（可选）

如果你处于中国大陆网络环境，且没有稳定的代理工具，可以配置 Flutter 国内镜像，以提高依赖和 Flutter 资源的下载稳定性。

如果你已经有稳定可用的代理，并且可以正常访问 Flutter 官方资源，则可以跳过本节。

新建用户变量：

```text
变量名：PUB_HOSTED_URL
变量值：https://pub.flutter-io.cn
```

```text
变量名：FLUTTER_STORAGE_BASE_URL
变量值：https://storage.flutter-io.cn
```

这两个变量分别用于 Dart Package 和 Flutter 相关资源的国内镜像下载。

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_9_2026-09-15_16-14-34.jpg)

配置好后如图所示：

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_10_2026-09-15_16-14-34.jpg)

#### 将 Flutter 加入 Path

编辑用户变量中的`Path`，新增一条：

```text
C:\flutter\bin [此处应改为你的`flutter/bin`文件夹的路径]
```

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_11_2026-09-15_16-14-34.jpg)

### 4. 检查配置情况

修改环境变量后，已经打开的 `PowerShell` 不会自动读取新配置，关闭并重新打开终端，执行：

```powershell
flutter --version
dart --version
where.exe flutter
```

正常情况下应该能够看到 Flutter 和 Dart 的版本信息，`where.exe flutter` 应指向刚才安装的 Flutter，例如：

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_12_2026-09-15_16-14-34.jpg)

执行以下的指令，确认`[✓] Flutter`一项显示为正常：

```powershell
flutter doctor -v
```

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_13_2026-09-15_16-14-34.jpg)
---

## 三、安装 Android Studio

Flutter Android 开发需要 Android SDK、Platform Tools、模拟器等工具，此处推荐通过 Android Studio 统一管理。

在 Google 官方中国站下载 Windows 版本的安装程序并运行：

```text
https://developer.android.google.cn/studio
```

安装过程中一般保持默认配置即可。

点击下载安装程序

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_15_2026-09-15_16-14-34.jpg)

一路下拉到底选择确认

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_14_2026-09-15_16-14-34.jpg)

勾选虚拟设备选项

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_16_2026-09-15_16-14-34.jpg)

根据自身情况自定义路径

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_17_2026-09-15_16-14-34.jpg)

选不选都行，我这里选了不创建

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_18_2026-09-15_16-14-34.jpg)

按自己喜好来，我选了否

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_19_2026-09-15_16-14-34.jpg)

此处直接选择 `Standard` 即可，如有需要，可以选择 `Custom` 修改`Android Studio` 与 `Android SDK` 存储位置

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_42_2026-09-15_16-14-34.jpg)

确认设置ok就点 `next` ，想改的话点击 `Previous` 回到上一步修改

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_20_2026-09-15_16-14-34.jpg)

确认之后进入安装，结束后出现如下界面。

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_21_2026-09-15_16-14-34.jpg)

---

## 四、配置 Android SDK

Android Studio 首次启动完成后，在欢迎页面进入`SDK Manager`

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_26_2026-09-15_16-14-34.jpg)

### 1. SDK Platforms

选择`SDK Platforms`

安装`Android 16`
![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_24_2026-09-15_16-14-34.jpg)

### 2. SDK Tools

切换到`SDK Tools`，安装以下组件：

```text
Android SDK Build-Tools
Android SDK Command-line Tools (latest)
Android Emulator
Android SDK Platform-Tools
```

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_23_2026-09-15_16-14-34.jpg)

### 3. Android SDK 路径

Android Studio 默认一般会将 SDK 安装在：

```text
C:\Users\<用户名>\AppData\Local\Android\Sdk
```

如果选择了自定义路径，可能需要在应用内手动更改sdk路径

---

## 五、安装 Android Studio Flutter 插件

回到 Android Studio 欢迎页面，在左侧选择`Plugins`

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_27_2026-09-15_16-14-34.jpg)

搜索`Flutter`，安装由 `Google` 提供的 `Flutter` 插件，安装完成后重启 Android Studio。

---

## 六、调试设备

### 1. 创建 Android 模拟器

在 Android Studio 中进入`Virtual Device Manager`，或者在项目中进入 `Tools → Device Manager` 创建一个虚拟设备。

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_29_2026-09-15_16-14-34.jpg)
![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_30_2026-09-15_16-14-34.jpg)

设备型号没有严格要求，系统镜像建议选择 `Android 16 API 36`

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_31_2026-09-15_16-14-34.jpg)

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_32_2026-09-15_16-14-34.jpg)

创建完成后启动模拟器

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_33_2026-09-15_16-14-34.jpg)

然后在 PowerShell 中执行 `flutter devices` ，如果能够看到类似下图的输出，说明 Flutter 已经成功识别 Android 模拟器。

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_34_2026-09-15_16-14-34.jpg)

---

### 2. 使用 Android 真机调试（可选）

如果希望使用 Android 手机进行调试：

1. 在手机设置中开启“开发者模式”；
2. 开启“USB 调试”；
3. 使用支持数据传输的数据线连接电脑；
4. 手机上出现授权提示时允许该电脑进行 USB 调试。

不同厂商进入开发者模式的方式可能不同，可以根据自己的手机型号搜索对应教程。

连接后执行 `flutter devices` 指令，如果能够看到自己的手机，说明连接成功。

---

## 七、再次检查开发环境

执行：

```powershell
flutter doctor -v
```

应能够正常识别：

```text
Flutter
Android toolchain
Android Studio
```

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_41_2026-09-15_16-14-34.jpg)

<!-- ### 关于 Android License

部分旧版本 Android SDK 会要求执行 `flutter doctor --android-licenses` ，然后不断输入 `y` 接受协议。

但是新版 Android Command-line Tools 已经调整了 license 管理方式，可能出现：

```text
Warning: The --licenses option is no longer needed.
```

![license](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_28_2026-09-15_16-14-34.jpg)

同时 `flutter doctor` 指令仍有可能提示 `Android license status unknown`

> 最终是否配置成功，应结合 `flutter devices` 和实际运行 Flutter App 判断 -->

---

## 八、创建第一个 Flutter 项目

环境基本配置完成后，我们创建一个测试项目。

打开 Android Studio ，点击 `New Flutter Project`

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_35_2026-09-15_16-14-34.jpg)

### 1. Flutter SDK path

Generators选择 `Flutter` ，路径选择刚才安装的 Flutter SDK：

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_36_2026-09-15_16-14-34.jpg)

### 2. 项目配置

按照图片上这样选即可，点击 `create` 创建项目。

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_37_2026-09-15_16-14-34.jpg)

```text
Project name: test_app
Organization: com.example
Android language: Kotlin
Platforms：Android iOS
```

---

### 3. 运行 Flutter Demo

完成后会自动创建出一个计数器的demo,如下图所示。

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_38_2026-09-15_16-14-34.jpg)

先启动刚才创建的 Android 模拟器，然后在 Android Studio 右上方选择对应的 Android Emulator，点击绿色运行按钮。

也可以在项目目录执行

```powershell
flutter run
```

如果存在多个设备，可以先执行 `flutter devices` 查看设备 ID，例如 `emulator-5554` ，然后指定运行设备

```powershell
flutter run -d emulator-5554
```

最后，模拟器中会出现 Flutter 默认 Demo 页面，至此，Flutter Android 开发环境配置完成。

![](https://raw.githubusercontent.com/Patricia-Chi/twt-mobile-guide/main/assets/flutter_setup/photo_40_2026-09-15_16-14-34.jpg)

---

## 九、运行微北洋项目

测试项目可以正常运行后，就可以尝试运行移动组维护的微北洋项目。

项目仓库：

```text
https://github.com/twtstudio/WePeiYang-Flutter
```

安装 Dart / Flutter 依赖执行：

```powershell
flutter pub get
```

第一次运行项目时可能需要下载较多内容，等待时间会很长。

---

## 配置完成，恭喜你喵！

完成这些配置并成功运行第一个 Flutter App 后，就可以继续学习 Dart、Flutter Widget、State、网络请求等内容，并开始尝试阅读和参与微北洋项目！加油！

欢迎加入天外天工作室移动组！

## 勘误与反馈

由于 Flutter、Android Studio 和 Android SDK 都在持续更新，本文中的部分界面、版本号或操作步骤可能会随时间发生变化。

如果你在阅读或配置过程中发现：

- 文档内容有错误或遗漏；
- 某些步骤已经过时；
- 按照文档操作后仍然无法正常配置环境；

欢迎通过 GitHub Issue 或其他方式联系我，我会尽量及时更新文档。
本文仓库地址：https://github.com/Patricia-Chi/twt-mobile-guide  
可以在[我的博客](https://patricia-chi.github.io)在线查看:https://patricia-chi.github.io/2026/09/15/配置Flutter开发环境
