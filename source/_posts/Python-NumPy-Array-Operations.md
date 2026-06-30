---
title: Python NumPy Array Operations
date: 2024-01-25 21:15:04
tags:
categories:
  - [Python, Package]
---


1. NumPy是用于处理数组的python库
2. NumPy中的数组对象称为ndarray，它提供了这么多支持函数，使得利用ndarray非常容易
3. Pip install numpy
4. Import numpy as np
5. Np.array()，指定数组维数ndmin，获取数组维数arr.ndim
6. 索引维度访问[]
7. 负索引 从尾开始访问数组
8. 切片（正负索引）
		i. [start:end:step]
			1) 不传递start，则视为0
			2) 不传递end，则视为数组长度
			3) 不传递step，视为1
9. 数据类型
10. 副本和视图
		i. 副本拥有数据，对副本所做的任何更改都不会影响原始数组，对原始数组所做的任何更改也不会影响副本
		ii. 视图不拥有数据，对视图所做的任何更改都会影响原始数组，而对原始数组所做的任何更改都会影响视图
		iii. base属性
			1) 如果该数组拥有数据，则这个base属性返回None
11. 数组形状
		i. NumPy数组有一个名为shape的属性，该属性返回一个元组，每个索引具有相应元素的数量
12. 数组重塑
		i. 一维to多维
		ii. 多维to一维（展平数组）
13. 数组迭代
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
1.  数组创建
	a. Arr = np.array([1,2,3,4,5])
	b. 可以将列表、元组或任何类似数组的对象传递给array()方法，然后它将被转换为ndarray
2.  数组连接
	a. Np.concatenate((arr1,arr2), axis=1)
	b. 堆栈函数连接
		i. Np.statck
		ii. Dstack
		iii. Hstack
		iv. Vstack
3.  数组拆分
	a. Np.array_split
		i. axis参数指定要拆分的轴
	b. 与hstack()相反的hsplit()
4.  数组搜索
	a. Np.where(arr==4)
	b. Np.where(arr%2==0)
	c. Np.searchsorted(arr,7, [side='right']) 在数组中执行二进制搜索，并返回将在其中插入指定值以维持搜索顺序的索引
5.  数组排序
	a. Np.sort(arr)
		i. 返回数组的副本，而原始数组保持不变
		ii. 如果在二维数组上使用sort()方法，则将对两个数组进行排序
6.  NumPy数组过滤 filtering
	a. Filter_arr = arr > 62
newarr = arr[filter_arr]
	b. Filter_arr = [True, False, True, False, True]
1.  NumPy中的随机数
	a. Random.randint(100)
	b. Random.rand() 0到100之间的随机浮点数
	c. Random.randint(100, size=(5)) 生成一维随机数组
	d. Random.randint(100, size=(3,5)) 生成有3行的2-D数组，每行包含5个从0到100之间的随机整数
	e. Random.rand(5) 生成含5个随机浮点数的一维数组
	f. Random.rand(3,5) 生成有3行的2-D数组，每行包含5个随机数
	g. Random.choice([3,5,7,9] 从数组中生成随机数 也可以接受size参数生成数组
2.  Ufuncs
	a. Ufuncs指的是Universal Functions，它们是对ndarray对象进行操作的NumPy函数
	b. ufunc用于在NumPy中实现矢量化，这比迭代元素养要快得多（将迭代语句转换为基于向量的操作称为向量化）
	c. 提供广播和其他方法，例如减少、累加等

	
		
