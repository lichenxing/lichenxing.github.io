---
title: hello domain
date: 2024-05-18 19:39:22
tags: hexo
---
将hexo博客部署到个人域名上

# 域名购买

我是在腾讯云买的 首年45元 价格相对实惠
购买的基本流程就是进入腾讯云官网
进入控制台进行域名注册然后付钱买选择的域名就行
https://www.tencentcloud.com/zh/products/domain
<!-- more -->
# 域名设置DNS解析

- 进入控制台
- 进入域名控制台
- 进行解析设置，添加这两条记录
  注意：这里的IP是ping yourname.github.io

# 创建 CNAME 文件

在hexo本地目录 source 目录下面新建一个文件，取名为 CNAME (无后缀)，内容就是你购买的域名
比如我的域名是chenxing.live

# 重新部署

```
hexo clean
hexo g 
hexo d
```

# 最终验证

输入自己的域名地址,比如我的就是这个 https://chenxing.live 进行验证。

