---
title: "Мощь MySQL"
date: ""
categories: 
  - "note"
tags: 
  - "mysql"
---

**ON DELETE CASCADE**

```
CREATE TABLE test1 (    id INTEGER NOT NULL,    parent INTEGER,    PRIMARY KEY (id),    FOREIGN KEY (parent) REFERENCES test1 (id)      ON UPDATE CASCADE      ON DELETE CASCADE  ); 
```

правило ON DELETE CASCADE, заданное для внешнего ключа по полю PARENT. Благодаря нему, при удалении узла будет автоматически удалено и все поддерево, для которого этот узел является корнем.  
  
**ON DUPLICATE KEY**

```
// находим объект $row = query('SELECT * FROM table WHERE id=1'); // проверяем есть ли такой объект if ($row) { // делаем апдейт query('UPDATE table SET column=column+1 WHERE id=1'); } else { // делаем вставку query('INSERT INTO table SET column=1, id=1'); }
```

Можно заменить на запрос без php

```
INSERT INTO table SET column = 1, id=1 ON DUPLICATE KEY UPDATE column = column + 1
```

  
  
**INSERT IGNORE**

```
// находим объект $row = query('SELECT * FROM table WHERE id=1'); // если такого объекта нет, то вставляем новую запись if (!$row) { query('INSERT INTO table …'); }
```

заменяем на запрос без php

```
INSERT IGNORE INTO table …
```
