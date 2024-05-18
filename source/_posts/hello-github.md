---
title: hello github
date: 2024-05-18 19:38:05
tags:
  - hexo
  - git
---
将个人博客源码也托管到github
关键点：分支切换 找到隐藏文件
<!-- more -->
# 配置步骤

## 1.本地电脑创建文件夹并进入该文件夹

```
mkdir chenxingBlogs
cd chenxingBlogs
```

## 2.将静态站托管仓库克隆回本地

```
git clone https://github.com/lichenxing/lichenxing.github.io.git
```

## 3.新建分支并切换

```
# 新建并切换分支
git checkout -b source
```

备注：如果只是切换分支 git checkout 分支名。

## 4.清理文件

删除hexo自动生成的静态文件（注意保留.git目录）

在这一步要注意，.git文件是隐藏文件，mac电脑要看到隐藏文件需要【Command + Shift +】快捷命令打开。

## 5.添加hexo源码

将个人博客源码目录下的文件复制到此处。（注意删除原来的.git目录）。

## 6.同步代码到github
```
git add -A
git commit -m '初始化自动部署分支'
git push --set-upstream origin source
```
## 7.登录github检查自己的仓库中是否已经有了源码的分支
检查是否有「初始化自动部署分支」的提交。
# 参考文档

https://www.idzd.top/archives/1430/

# 注意事项

1. 在配置时或者操作时需要注意一下分支名称是否正确，如果不正确需要切换分支。
2. mac电脑显示隐藏文件快捷键：**Command + Shift + .** 在Finder打开你想要查看隐藏文件的文件夹，然后使用快捷键Command + Shift + .，即可查看当下文件夹中的隐藏文件。 要恢复隐藏文件的话再次按shift+cmmand+. ，即可恢复文件的隐藏状态
