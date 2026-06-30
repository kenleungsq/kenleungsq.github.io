---
title: Django Tutorial Views, Templates, and Models
date: 2024-01-27 17:51:42
tags:
categories:
  - [Python, Package, Django]
---

# Python 解释器 环境变量设置 pip

Settings -> type venv 创建虚拟环境 https://blog.csdn.net/bubblelone/article/details/106299654

# Django tutorial

you frequently work with views.py (that contains the functions that define pages in your web app)
models.py (that contains classes defining your data objects)

From <https://code.visualstudio.com/docs/python/tutorial-django> 

apps.py (app configuration), admin.py (for creating an administrative interface), and tests.py (for creating tests), which are not covered here.

From <https://code.visualstudio.com/docs/python/tutorial-django> 


```shell
django-admin startproject web_project .

python manage.py migrate

python manage.py startapp hello
```

*** 

command in your project folder (where manage.py resides):
{% asset_image image.png %}

# Hello world


涉及Urls.py views.py 


Set up launch.json 不用 runserver in terminal 直接F5

可debug，set断点

引用，设置templates

This template contains two placeholders for data values named "name", and "date", which are delineated by pairs of curly braces, &lbrace;&lbrace; and &rbrace;&rbrace;. 

{% asset_image image1.png %}

## 传递两个参数
```Python
urlpatterns = [
    path("", views.home, name="home"),
    path("hello/<name>/<age>", views.hello_there, name="hello_there"),
]
```

## Static files
Serving static files requires that the INSTALLED_APPS list in settings.py contains django.contrib.staticfiles, which is included by default.

发布时把静态文件放到一个文件夹
For production deployments, you typically collect all the static files from your apps into a single folder using the python manage.py collectstatic command.

Managing static files (e.g. images, JavaScript, CSS)
https://docs.djangoproject.com/en/3.1/howto/static-files/


## 使用snippet 创建多个相似的页面
Also, because you'll likely create many pages that extend the same template, it's helpful to create a code snippet in VS Code with which you can quickly initialize new page templates. A snippet helps you avoid tedious and error-prone copy-paste operations.

From <https://code.visualstudio.com/docs/python/tutorial-django> 

# Work with data, data models, and migrations

In Django, a model is a Python class, derived from django.db.models.Model

Other database mirgrate

如果执行python manage.py migrate遇到错误
If you see errors when running the commands, make sure you're not using a debugging terminal that's left over from previous steps, as they may not have the virtual environment activated.

From <https://code.visualstudio.com/docs/python/tutorial-django> 

文件组织架构

注意else的位置，否则会return None

```Python
if request.method == "POST":
        if form.is_valid():
            message = form.save(commit=False)
            message.log_date = datetime.now()
            message.save()
            return redirect("home")
else:
     return render(request, "hello/log_message.html", {"form":form})
```


继承类及引用父类中的方法
```Python
Class a(parent)

Def funcA():
	Super(a,self).
```
	
	
新建LogMessage类，migrate到数据库表
Urls.py中定义context变量
html中用if, for等
```html
{% for message in message_list %}
{% endfor %}
```
Home中再读取

[Django form用法](https://blog.csdn.net/qq_24861509/article/details/46506315?spm=1001.2101.3001.6661.1&utm_medium=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7Edefault-1.no_search_link&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7Edefault-1.no_search_link&utm_relevant_index=1)

Create multiple templates that extend a base template
类似于C# rendor 的概念
