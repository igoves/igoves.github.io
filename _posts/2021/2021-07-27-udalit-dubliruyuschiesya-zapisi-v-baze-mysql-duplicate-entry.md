---
title: "Удалить дублирующиеся записи в базе mysql (duplicate entry)"
date: ""
categories: 
  - "note"
tags: 
  - "mysql"
---

Создаем чистую таблицу аналогичной то что у нас есть с неуниклаьными значениями

```
CREATE TABLE clean LIKE options
```

  
Создаем индексы для нужных полей

```
ALTER IGNORE TABLE clean ADD UNIQUE INDEX (add1, add2, add3)
```

  
Дальше вставляем данные из нашей старой базы в новую с параметром IGNORE

```
INSERT IGNORE INTO clean SELECT * FROM options
```

  
Удаляем старую таблицу

```
DROP TABLE options
```

  
И переименовываем новую в старую

```
RENAME TABLE clean TO options
```
