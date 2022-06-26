---
title: "Узнать следующую и предыдущую запись MySQL"
date: ""
categories: 
  - "note"
---

```
+----+---------------------+| id | date                |+----+---------------------+|  1 | 2012-08-06 22:09:40 ||  2 | 2012-08-06 22:09:44 ||  3 | 2012-08-06 22:10:00 ||  4 | 2012-08-06 22:10:00 ||  5 | 2012-08-06 22:10:17 |+----+---------------------+
```

  
Следующая запись:  

```
SELECT *FROM `table`WHERE `date` > $date OR (`date` = $date AND `id` > $id)ORDER BY `date` ASC, `id` ASCLIMIT 1
```

  
Предыдущая запись:  

```
SELECT *FROM `table`WHERE `date` < $date OR (`date` = $date AND `id` < $id)ORDER BY `date` DESC, `id` DESCLIMIT 1
```
