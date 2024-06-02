---
title: hello django
date: 2024-06-02 21:44:12
tags: django
---
## 问题描述
from django.conf.urls import url # 用 url 需要引入
ImportError: cannot import name 'url' from 'django.conf.urls' (/Users/oo/PycharmProjects/djangolearn001/.venv/lib/python3.9/site-packages/django/conf/urls/__init__.py)

## 问题原因
这是因为在Django 4.0及更高版本中，django.conf.urls.url已被移除。取而代之的是使用django.urls.path和django.urls.re_path。

## 问题解决

将原来的url()调用替换为path()或re_path()

```
from django.urls import path, re_path
from . import viewsurlpatterns = [
path('example/', views.example_view, name='example'),
re_path(r'^example-regex/$', views.example_view, name='example-regex'),
]
```
