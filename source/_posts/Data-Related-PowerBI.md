---
title: PowerBI
date: 2024-01-29 15:05:55
tags:
categories:
  - [Data, Power BI]
---

# 切片联动

Power BI 把在周期边上断掉的星期计算在内
把周做成筛选项，或把周做成度量

Related 只能用在新建列，不能用在度量值？

现在只能做到先通过TREM切片器，筛选出week of year，再通过切换week of year去联动图
不能直接筛选week of year联动图
可以做到了，通过下面这样添加

{% asset_image image.png %}

# Power BI can't connect to MySQL

{% asset_image image1.png %}

Solution:

{% asset_image image2.png %}
