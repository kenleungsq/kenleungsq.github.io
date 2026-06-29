---
title: Django根据MySQL数据库中已经存在的表反向生成models.py
date: 2024-01-28 19:57:12
tags:
categories:
  - [Python, Package, Django]
---

https://blog.csdn.net/tianxinyiru/article/details/107836918

从Django模型 migrate到数据库
	1. 加入INSTALLED_APPS
	2. 只migrate新加入的APP

{% asset_image image.png %}

# 从数据库生成model后，runserver，报错：

ValueError: source code string cannot contain null bytes
解决:
https://blog.csdn.net/changyana/article/details/122795234

{% asset_image image1.png %}


# Runserver 报错：

RuntimeError: Model class dashboard.models.BookList doesn't declare an explicit app_label and isn't in an application in INSTALLED_APPS.
到setting.py加入自建的APP


从指定数据库获取数据
排序
输出
{% asset_image image3.png %}
