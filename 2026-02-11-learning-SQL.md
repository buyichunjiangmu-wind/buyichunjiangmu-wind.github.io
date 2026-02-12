---
title: SQL SELECT 
date: 2026-02-11 14:00:00 +0800
categories: [SQL]
abstract : 以鱼皮的SQL之母作为资料来源，自学SQL整理的学习笔记
---
设定一个表格students

# 一、基础知识（select，where，order by，limit，distinct，聚合函数，having）
SELECT 基础查询
```
select * from students;
```
*内填查询的列 select name from student；
WHERE 条件过滤
```
```
ORDER BY 排序
```
```
LIMIT 分页
``````
DISTINCT 去重

COUNT / SUM / AVG 聚合函数

GROUP BY 分组

HAVING 与 WHERE 的区别



---

# 二、多表查询（join，子查询，exists，in）
##主键与外键

INNER JOIN

LEFT JOIN

RIGHT JOIN

多表 JOIN 实战

子查询（Subquery）

EXISTS 与 IN 的区别




---

# 三、进阶（case when ,union/union all,row_number,rank,窗口函数）
##CASE WHEN

UNION / UNION ALL

窗口函数（OVER）

ROW_NUMBER

RANK 与 DENSE_RANK



