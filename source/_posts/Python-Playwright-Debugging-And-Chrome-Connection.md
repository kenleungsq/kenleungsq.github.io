---
title: Python Playwright Debugging and Chrome Connection
date: 2024-01-28 19:16:04
tags:
categories:
  - [Automation, Python Tools]
---

# Tutorial
https://playwright.dev/python/docs/intro
https://blog.csdn.net/karl41/article/details/119334408

# How to Debug and Run

{% asset_image image.png %}

# 连接已打开的Chrome

https://blog.csdn.net/weixin_44791551/article/details/124719506
输入：chrome.exe --remote-debugging-port=9527 --user-data-dir=“D:\AutomationProfile” ，并回车。
这句代码的意思是启动 chrome浏览器 的调试模式。
chrome.exe -remote-debugging-port=9527 -user-data-dir="D:\AutomationProfile"

{% asset_image image1.png %}
