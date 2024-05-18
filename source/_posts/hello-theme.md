---
title: hello theme
date: 2024-05-18 19:34:45
tags: hexo 
---
对个人博客的主题进行更换。

## 步骤简介

1. 进入hexo官网挑选自己喜欢的主题 https://hexo.io/themes/
2. 确定选择icarus主题，下载icarus主题 https://github.com/ppoffice/hexo-theme-icarus
3. 更换配置文件 https://github.com/ppoffice/hexo-theme-icarus

## 遇到的问题

hexo clean时报错 prism_plugin

**现象**

```
ERROR Plugin load failed: hexo-prism-plugin Error: `prism_plugin` options should be added to _config.yml file at /Users/oo/myblogs/node_modules/hexo-prism-plugin/src/index.js:70:9 at /Users/oo/myblogs/node_modules/hexo/dist/hexo/index.js:255:20
```

**解决**

在_config.yml文件中增加下面代码

```
prism_plugin:
mode: 'preprocess' # realtime/preprocess
theme: 'default'
line_number: false # default false
```

