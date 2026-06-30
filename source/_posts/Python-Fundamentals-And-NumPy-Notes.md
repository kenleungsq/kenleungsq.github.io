---
title: Python Fundamentals and NumPy Notes
date: 2024-01-25 18:35:22
tags:
categories:
  - [Python, Concept]
---

	1. 用于
		a. Web开发（服务器端）
		b. 软件开发
		c. 数学
		d. 系统脚本
	2. 可以做什么
		a. 可以在服务器上使用Python来创建Web应用程序
		b. 可以与软件一起使用来创建工作流
		c. 可以连接数据库系统，可以读取和修改文件
		d. 可以用于处理大数据并执行复杂的数学运算
		e. 可肜于快速原型设计，也可用于生产就绪的软件开发
	3. 为何选择Python
		a. 跨平台
		b. 在解释器系统上运行，代码可以在编写后立即执行
		c. 可以以程序方式、面向对象的方式或功能方式来处理
		
	4. 变量
		a. 变量名区分大小写
		b. global关键字，在函数内声明变量，函数外部也可使用
		c. 变量赋值时，确定类型
		d. 构造函数完成变量类型转换，int(), float(), str()
	5. 字符串
		a. 字面量
			i. 单引号与双引号一样
			ii. 三引号用于多行字符
		b. 字符串是数组
			i. 裁切
			ii. 负的索引
			iii. 检查字符串，in 或 not in
		c. 插值
			i. Format()
	6. 列表
		a. 一个有序且可更改的集合，用方括号表示。
	7. 元组
		a. 有序且不可更改的集合，用圆括号表示。
	8. 集合
		a. 无序和无索引，用花括号。
	9. 字典
	10. Lambda
		a. 如果在短时间内需要匿名函数，使用lambda函数
	11. python没有内置数组，可使用列表代替
	12. 类/对象
		a. _init_()函数，构造函数
		b. self参数是对类的当前实例的引用，用于访问属于该类的变量
			i. 不必被命名为self，但它必须是类中任意函数的首个参数
		c. 类定义不能为空，写了无内容的类定义语句，使用pass 语句来避免错误
	13. 继承
		a. Class student(person)
		b. 子的_init_()函数会覆盖对父的_init_()函数的继承，如需保持父的_init_()函数的继承，添加对父的__init__()调用

		class Student(Person):
  def __init__(self, fname, lname):
    Person.__init__(self, fname, lname)
		
		From <https://www.w3school.com.cn/python/python_inheritance.asp> 
		
		c. Super()函数，使子类从其父继承所有方法和属性

		class Student(Person):
  def __init__(self, fname, lname):
    super().__init__(fname, lname)
		
		From <https://www.w3school.com.cn/python/python_inheritance.asp> 
	1.  迭代器
		a. 字符串也是可迭代的对象
		b. 创建迭代器
			i. __iter__(self)
			ii. __next__(self)
		c. 为防止迭代永远进行，可以使用StopoIteration
	2.  模块
	3.  JSON
	4.  PIP
		a. Python包或模块的包管理器
	5.  Try except finally
	6.  NumPy
		a. NumPy是用于处理数组的python库
		b. NumPy中的数组对象称为ndarray，它提供了这么多支持函数，使得利用ndarray非常容易
		c. Pip install numpy
		d. Import numpy as np
		e. Np.array()，指定数组维数ndmin，获取数组维数arr.ndim
		f. 索引维度访问[]
		g. 负索引 从尾开始访问数组
		h. 切片（正负索引）
			i. [start:end:step]
				1) 不传递start，则视为0
				2) 不传递end，则视为数组长度
				3) 不传递step，视为1
		i. 数据类型
		j. 副本和视图
			i. 副本拥有数据，对副本所做的任何更改都不会影响原始数组，对原始数组所做的任何更改也不会影响副本
			ii. 视图不拥有数据，对视图所做的任何更改都会影响原始数组，而对原始数组所做的任何更改都会影响视图
			iii. base属性
				4) 如果该数组拥有数据，则这个base属性返回None
		k. 数组形状
			i. NumPy数组有一个名为shape的属性，该属性返回一个元组，每个索引具有相应元素的数量
		l. 数组重塑
			i. 一维to多维
			ii. 多维to一维（展平数组）
		m. 数组迭代
			i. For x in arr
			ii. For x in np.nditer(arr)（迭代每个标量）
			iii. 以不同数据类型迭代数组 
			for x in np.nditer(arr, flags=['buffered'], op_dtypes=['S']):
			
			From <https://www.w3school.com.cn/python/numpy_array_iterating.asp> 
			
			iv. Ndenumerate() 迭代时如需要获取索引

			for idx, x in np.ndenumerate(arr):
  print(idx, x)
			
			From <https://www.w3school.com.cn/python/numpy_array_iterating.asp> 
			v. 以不同步长迭代d
		
