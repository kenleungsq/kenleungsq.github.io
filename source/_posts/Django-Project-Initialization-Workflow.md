---
title: Django Project Initialization Workflow
date: 2024-01-27 18:07:32
tags:
categories:
  - [Python, Package, Django]
---

1. Create virtual environmentVirtualenv 
2. Pip install django
3. Create a sitedjango-admin startproject mysite
4. Ctrl-c to ctrl-breakPicture on page "Process map"
5. Migrate table to database
```shell
$ python manage.py migrate
```
1. Add modelsPicture on page "Process map"
2. Add to installed appPicture on page "Process map"
3. Make migration file python manage.py makemigrations polls
4. Django模型层自带ORM系统，会自动为每个模型创建数据库访问的API
5.  创建admin帐号 在admin中增加自定义类
