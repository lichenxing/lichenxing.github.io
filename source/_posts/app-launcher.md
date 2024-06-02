---
title: app-launcher
date: 2024-06-02 10:33:24
tags: launcher
---
通过 adb shell 命令直接设置默认启动器

## 确认设备连接
`adb devices`

## 列出所有已安装的包名
`adb shell pm list packages`

## 查找应用主活动
`adb shell dumpsys package 应用包名 | grep -A 100 'Activity'
adb shell dumpsys package com.rokid.glass.dxeducation | grep -A 100 'Activity'`

## 设置launcher
`adb shell cmd package set-home-activity  应用包名/.activity.主活动
adb shell cmd package set-home-activity  com.rokid.glass.dxeducation/.activity.UserGuideActivity`