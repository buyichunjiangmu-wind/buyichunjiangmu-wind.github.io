---
title: SQL SELECT 
date: 2026-02-11 14:00:00 +0800
categories: [SQL]
abstract : 以程序员鱼皮创造的网页--SQL之母作为资料来源，整理的学习笔记
---
设定一个表格students，内有name，score，age等信息

# 一、基础知识（select，where，order by，limit，distinct，聚合函数，having，条件分支，时间函数）
1.SELECT 基础查询
```sql
select * from students;
```
*内填需要查询的列 select name from student,from 后表格名,";"可有可无，英文可大写也可小写
别名语法
```sql
select * from students as "别名"
```
2.WHERE 条件过滤，特定查询，where后为固定查询的列或行
```sql
select* from students where name="*"
```
之后会输出关于 name是*的相关内容，where后加运算符表示特定条件咨询'!=','>','<''is null'(空值)

模糊咨询,关键词咨询，下文代码会输出没有关键词*的列，and和or也可使用作为判断
```sql
seclec name frome students where name not like'%*%'
seclec name frome students where name not like'%*%'，or score>200;
```
3.ORDER BY 排序，下文表示用score排序，desc降序，asc升序
```sql
select name, age, score from student order by score desc, age asc;
```
4.DISTINCT 去重,distinct会输出class_id 的不同值，达到去重
```sql
select distinct class_id, exam_num from student;
```
5.COUNT / SUM / AVG 聚合函数
在 SQL 中，聚合函数是一类用于对数据集进行 汇总计算 的特殊函数。它们可以对一组数据执行诸如计数、求和、平均值、最大值和最小值等操作。聚合函数通常在 SELECT 语句中配合 GROUP BY 子句使用，用于对分组后的数据进行汇总分析。（抄的）但要注意计数是否有重复值，采用去重函数distinct
COUNT：计算指定列的行数或非空值的数量。
SUM：计算指定列的数值之和。
AVG：计算指定列的数值平均值。
MAX：找出指定列的最大值。
MIN：找出指定列的最小值。
例如计算总金额
```sql
SELECT SUM(amount) AS total_amount
FROM orders;
```
6.GROUP BY 分组
在SQL 中，通常使用 GROUP BY 关键字对数据进行分组，下面的代码表示将customer_id分好组，然后再计算每个customer_id的order_id数目
```sql
SELECT customer_id, COUNT(order_id) AS order_num
FROM orders
GROUP BY customer_id;
```
但是如果是多个分组，在GROUP BY后添加即可
7.LIMIT 截断,下文表示从第 2 条数据开始、截取 3 个学生的信息。第一个数字表示一次先获取一条信息，获取后从表中清除，第二个数字表示再获取几条信息
```sql
select name, age from student order by age asc limit 1, 3;
```


8.HAVING 与 WHERE 的区别
HAVING 子句与条件查询 WHERE 子句的区别在于，WHERE 子句用于在 分组之前 进行过滤，而 HAVING 子句用于在 分组之后 进行过滤（抄的），意思是having一定要在group by之后

9.条件分支,示例语法如下
```sql
CASE WHEN (条件1) THEN 结果1
	   WHEN (条件2) THEN 结果2
	   ...
	   ELSE 其他结果 END
```
when后为一个条件，有点相似于limit截断，第一个条件就分层。
```sql
SELECT
  name,
  CASE WHEN (age > 60) THEN '老同学'
       WHEN (age > 20) THEN '年轻'
       ELSE '小同学' END AS age_level
FROM
  student
ORDER BY
  name asc;
```
10.时间函数
时间函数是为查询时间的函数，注意，这里的日期、日期时间和时间将根据当前的系统时间来生成，实际运行结果可能会因为当前时间而不同
DATE：获取当前日期
DATETIME：获取当前日期时间
TIME：获取当前时间
```sql
select name, date() as 当前日期 from student
```
select后面都是要查询的东西，查询为date（当前日期）

---

# 二、多表查询（join，子查询，exists，in）
##主键与外键


1.关联查询
CROSS JOIN
将表1中的部分数据和表2的部分数据整合成新的表3，from 后的employees 指代为e，即e.emp_name是从employees的一部分数据

```sql
SELECT e.emp_name, e.salary, d.department, d.manager
FROM employees e
CROSS JOIN departments d;
```

简化为

```sql
SELECT e.emp_name, e.salary, d.department, d.manager
FROM employees e, departments d;
```

INNER JOIN
把两个表的相同表头的数据合并，下文的代码表示employees表加入（join）department表，把两个表的department的部分合并
```
SELECT e.emp_name, e.salary, e.department, d.manager
FROM employees e
JOIN departments d ON e.department = d.department;
```
LEFT JOIN

RIGHT JOIN


2.子查询（Subquery）




EXISTS 与 IN 的区别




---

# 三、进阶（case when ,union/union all,row_number,rank,窗口函数）
##CASE WHEN

UNION / UNION ALL

窗口函数（OVER）

ROW_NUMBER

RANK 与 DENSE_RANK



