---
title: 数据库语句
date: 2024-01-24 22:00:18
tags:
categories:
  - Database
---

	1. 通配符
		a. % 代表零个或多个字符
		b. _ 仅替代一个字符
		c. [charlist] 字符列中的任何单一字符
		d. [^charlist]或[!charlist]  不在字符列中的任何单一字符
	2. Between And
	3. Join
		a. Join(inner join): 如果表中有至少一个匹配，则返回行
		b. Left join： 即使右表中没有匹配，也从左表返回所有的行
		c. Right join： 即使左表中没有匹配，也从右表返回所有的行
		d. Full join：只要其中一个表中存在匹配，就返回行
	4. UNION
		a. 用于合并两个或多个SELECT语句的结果集
		b. SELECT语句必须拥有相同数量的列。列也必须拥有相似的数据类型。同时，每条SELECT语句中的列的顺序必须相同
	5. SELECT INTO
		a. 用于创建表的备份复件
		b. IN 子句可用于向另一个数据库中拷贝表：
SELECT *
INTO new_table_name [IN externaldatabase] 
FROM old_tablename

	1. CREATE VIEW
		a. 视图是基于SQL语句的结果集的可视化的表
		b. 好处
			i. 定制用户数据，聚集特定的数据
			ii. 简化数据操作 select * from view1
			iii. 基表中的数据有了一定的安全性
			iv. 合并分离的数据，创建分区视图 union
		c. 限制
			i. 定义视图时不能使用orderby
	2. 函数
		a. Aggregate 函数
			i. 面向一系列的值，并返回一个单一的值
			ii. AVG, COUNT, FIRST, LAST MAX, MIN, SUM等
		b. Scalar函数
			i. 面向某个单一的值，并返回基于输入值的一个单一的值
			ii. Format() 对字段的显示进行格式化
	3. 事务处理
		a. 事务具有原子性、一致性、隔离性、持久性
		b. 常用语句
			i. Begin Transaction
			ii. Commit Transaction
			iii. Rollback Transaction
			iv. Save Transaction
	4. 集合运算
		a. 加法 union
		b. 包含重复行的加法 union all
		c. 选取表中的公共部分 intersect
		d. 减法 except
	5.  窗口函数
		a. <窗口函数> over (
		partition by a.associates order by a.associates) as number,a.*
		from A as a)
		b. 专用窗口函数：rank, dense_rank, row_number
	6.  流程控制
		Begin end:用于将多个SQL语句组合为一个逻辑块
		IF 选择判断结构
		IF ELSE
		CASE WHEN
		While 循环结构 配合begin end:while begin break continue end
		Rerurn ：从查询过程中无条件退出，位于其后的语句均不会被执行
		Goto :改变程序的执行的流程，使程序跳转到标识符指定的程序往下进行
		Waitfor:指定触发器存储过程或事物执行的时间时间间隔或事件，还可以用来暂时停止程序的执行，直到所设定的等待时间已过才继续往下执行
		declare @name char(20)
		set @name='静怡'
		waitfor delay'00:00:05'
		print '我最爱的电影是'+@name
		

# Rank
Assigns a number to a row
	• Ranking function indicates numeric rank relative to other rows
	• Ordered value used to calculate
	• May be unique, depending on ranking function used

What is the difference between these two?
Select name, row_number() over(order by         )
Select name, rank() over(order by         )

-- use CTE to enable paging(create a function)
{% asset_img image1.png This is an example image %}


Dense_Rank
	• Same value means same rank
	• Contiguous <- dense

Select name, dense_rank() over (order by     )


# Ntile

-- break into percentiles
Select [first name], [last name], [base rate],
Ntile(100) over (order by [base rate]) as percentile
From employees
Order by percentile desc

# Partitioning

# Query plan

The SQL Server execution plan(query plan) is a set of instructions that describes which process steps are performed while a query is executed by the database engine. The query plans are generated by the query optimizer and its essential goal is to generate the most efficient (optimum) and economical query plan

# [Insert Into语句的四种写法](https://blog.csdn.net/wangqingbo0829/article/details/52353085)

