---
title: mac上MySQL启动后立即停止
date: 2024-05-30 11:36:11
tags: mysql
---
## 问题描述：
在System Preference中，进入MySQL，当点击Start MySQL Server时，左侧的红色变成绿色后，立即又变成了红色，启动后立即又停止了!
## 解决方法：
在命令行中进行操作
### 启动
`sudo /usr/local/mysql/support-files/mysql.server start`
### 停止
`sudo /usr/local/mysql/support-files/mysql.server stop`
### 重启
`sudo /usr/local/mysql/support-files/mysql.server restart`
