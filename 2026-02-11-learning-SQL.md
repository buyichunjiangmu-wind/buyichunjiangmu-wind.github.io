
---
title: SQL SELECT 基础详解
date: 2026-02-11 14:00:00 +0800
categories: [SQL]
tags: [select, database]
---

# 一、什么是 SELECT？

SELECT 是 SQL 中最基础的查询语句，用来从数据库中获取数据。

---

# 二、基本语法

```sql
SELECT column1, column2
FROM table_name;
```

---

# 三、示例

```sql
SELECT * FROM users
WHERE age > 18;
```

