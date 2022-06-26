---
title: "Отсортировать вывод по IN - MySQL"
categories: 
  - "note"
tags: 
  - "in"
  - "mysql"
  - "sort"
  - "sortirovka"
---

Есть запрос  

```
SELECT * FROM table WHERE id IN (118,17,113,23,72)
```

Необходимо вывести значения таблицы в порядке который в IN, то есть, сначала 118 далее 17 и тд. Делается это так:  

```
SELECT * FROM table WHERE id IN (118,17,113,23,72) ORDER BY FIELD(id,118,17,113,23,72)
```
