---
title: Database DBMS and MySQL Fundamentals
date: 2024-01-24 21:54:39
tags:
  - Knowledge
categories:
  - Database
---

	1. 数据
		a. 定义：对客观事物的符号表示
		b. 种类：文字、图形、图像、声音
		c. 特点：数据与语义不可分
	2. 数据库
		a. 按照数据结构来组织、存储和管理数据的仓库
	3. 数据库管理系统
		a. DBMS
		b. RDBMS
	4. 数据库系统
		a. DBS
	5. 数据库优点
		a. 数据按一定的数据模型组织、描述和存储
		b. 可为各种用户共享
		c. 冗余度较小，节省存储空间
		d. 易扩展，编写有关数据库应用程序
	6. DBMS主要功能
		a. DDL
			i. DROP
			ii. CREATE
			iii. ALTER
			iv. GRANT
			v. REVOKE
		b. DML
			i. SELECT
			ii. INSEERT
			iii. DELETE
			iv. UPDATE
		c. 数据库的运行管理
			i. 保证数据的安全性、完整性
			ii. 多用户对数据的并发使用
			iii. 发生故障后的系统恢复
	7. DBMS分类
		a. 小型数据库
			i. Access
			ii. Foxbase
			iii. Sqlite
		b. 中型数据库
			i. MySql
			ii. Sql server
			iii. Infomix
		c. 大型数据库
			i. Sybase
			ii. Oracle
			iii. Db2
	8. B/S和C/S
	9. MySQL新特性
		a. 子查询
		b. 视图
		c. 存储过程
		d. 触发器
		e. 事务处理
		f. 热备份
		g. 二进制Bit类型
	10. MySQL数据类型
		a. 数值型
		b. 字符串
			i. 二进制数据类型（存储图像）
			ii. ……
		c. 日期和时间
		d. NULL
	11. 完整性约束
	12. 数据表类型
		a. MyISAM：成熟稳定
		b. InnoDB：加入事务、数据行级锁定机制、外键约束条件、崩溃恢复等新功能
		c. HEAP：只存在于内丰中，可做临时表
	13. 主键和外键
		a. 索引：优化查询速度
		b. 数据表之间的关联/引用关系是依赖具体的主键和外键建立起来的
		c. 主键：帮助MySQL以最快的速度把一条特定的数据记录的位置确定下来
		d. 外键：外键列类型尽可能与主键列类型保持一致，外键列应加上NOT NULL
	14. 主表和从表
		a. 当主表中没有对应的记录时，不能将记录添加到从表
