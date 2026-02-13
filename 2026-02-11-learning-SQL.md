---
title: SQL SELECT 
date: 2026-02-11 14:00:00 +0800
categories: [SQL]
abstract : 以鱼皮的SQL之母作为资料来源，整理的学习笔记
---
设定一个表格students，内有name，score，age等信息

# 一、基础知识（select，where，order by，limit，distinct，聚合函数，having，条件分支）
1.SELECT 基础查询
```
select * from students;
```
*内填需要查询的列 select name from student,from 后表格名,";"可有可无，英文可大写也可小写
别名语法
```
select * from students as "别名"
```
2.WHERE 条件过滤，特定查询，where后为固定查询的列或行
```
select* from students where name="*"
```
之后会输出关于 name是*的相关内容，where后加运算符表示特定条件咨询'!=','>','<''is null'(空值)

模糊咨询,关键词咨询，下文代码会输出没有关键词*的列，and和or也可使用作为判断
```
seclec name frome students where name not like'%*%'
seclec name frome students where name not like'%*%'，or score>200;
```
3.ORDER BY 排序，下文表示用score排序，desc降序，asc升序
```
select name, age, score from student order by score desc, age asc;
```
4.DISTINCT 去重,distinct会输出class_id 的不同值，达到去重
```
select distinct class_id, exam_num from student;
```
5.COUNT / SUM / AVG 聚合函数
```

```
6.LIMIT 截断,下文表示从第 2 条数据开始、截取 3 个学生的信息。第一个数字表示一次先获取一条信息，获取后从表中清除，第二个数字表示再获取几条信息
```
select name, age from student order by age asc limit 1, 3;
```
7.GROUP BY 分组

8.HAVING 与 WHERE 的区别

9.条件分支
```
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



