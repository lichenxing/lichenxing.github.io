---
title: hello menu
date: 2024-05-18 19:36:01
tags: hexo
---
自定义修改icarus的菜单，增删改新的菜单选项
比如增加关于、相册等

# 修改主题的配置文件_config.icarus.yml

```
menu:
主页: /
归档: /archives
分类: /categories
标签: /tags
相册: /photo
关于: /about
```

注意：后面路径为对应页面的路径，自己需要对照着在Git控制台汇总创建对应页面

# 在Git控制台中创建对应页面

从博客网站的根目录打开Git控制台，新建对应页面，例如：

```
hexo new page "about"
hexo new page "photo"
```

# 继续在控制台键入命令

```
hexo cl
hexo g
hexo s
```

# 重新加载博客主页验证

浏览器打开 http://localhost:4000/  新创建的菜单选项就成功了。
