---
title: hello adb
date: 2024-05-27 17:30:48
tags: adb
categories: adb
---
由于在干活过程中需要经常使用adb，所以抽空把adb常用的一些命令总结一下：

ADB（Android Debug Bridge）是一种功能强大的工具，可以用来管理和控制Android设备。以下是一些常用的ADB命令及其简要说明：

### 基本命令

1. **连接设备**
   ```sh
   adb devices
   ```
   列出所有连接的Android设备的序列号。

2. **启动ADB服务器**
   ```sh
   adb start-server
   ```
   启动ADB后台服务。

3. **停止ADB服务器**
   ```sh
   adb kill-server
   ```
   停止ADB后台服务。

### 文件操作

1. **推送文件到设备**
   ```sh
   adb push <本地文件路径> <设备目标路径>
   ```
   将文件从计算机推送到设备，例如：
   ```sh
   adb push example.txt /sdcard/Download/
   ```

2. **从设备拉取文件**
   ```sh
   adb pull <设备文件路径> <本地目标路径>
   ```
   从设备拉取文件到计算机，例如：
   ```sh
   adb pull /sdcard/Download/example.txt ./
   ```

### 应用管理

1. **安装应用**
   ```sh
   adb install <apk文件路径>
   ```
   安装APK文件到设备，例如：
   ```sh
   adb install example.apk
   ```

2. **卸载应用**
   ```sh
   adb uninstall <应用包名>
   ```
   卸载设备上的应用，例如：
   ```sh
   adb uninstall com.example.app
   ```

3. **列出已安装的应用**
   ```sh
   adb shell pm list packages
   ```
   列出设备上已安装的所有应用包名。

### 设备控制

1. **重启设备**
   ```sh
   adb reboot
   ```
   重启Android设备。

2. **重启到引导加载程序**
   ```sh
   adb reboot bootloader
   ```
   重启设备到引导加载程序模式。

3. **进入恢复模式**
   ```sh
   adb reboot recovery
   ```
   重启设备到恢复模式。

### 调试与日志

1. **启动Shell**
   ```sh
   adb shell
   ```
   启动设备上的命令行shell。

2. **查看日志**
   ```sh
   adb logcat
   ```
   查看设备的系统日志。

### 其他

1. **获取设备信息**
   ```sh
   adb shell getprop
   ```
   获取设备的属性信息。

2. **获取设备屏幕截图**
   ```sh
   adb shell screencap /sdcard/screenshot.png
   adb pull /sdcard/screenshot.png
   ```
   获取设备的屏幕截图并拉取到本地。

3. **录制屏幕**
   ```sh
   adb shell screenrecord /sdcard/demo.mp4
   adb pull /sdcard/demo.mp4
   ```
   录制设备的屏幕并拉取到本地。
