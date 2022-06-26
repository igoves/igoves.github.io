---
title: "Число тегов в облаке DLE"
date: ""
categories: 
  - "php"
tags: 
  - "dle"
  - "tegov"
  - "hak"
  - "chislo"
---

Хак, который позволит вам изменять количество выводимых меток (тегов) в блоке.  
  
Открываем файл \\\\engine\\\\modules\\\\tagscloud.php и ищем:  

```
$db->query("SELECT SQL_CALC_FOUND_ROWS tag, COUNT(*) AS count FROM " . PREFIX . "_tags GROUP BY tag ORDER BY count DESC LIMIT 0,40");
```

  
и заменяем на:  

```
$db->query("SELECT SQL_CALC_FOUND_ROWS tag, COUNT(*) AS count FROM " . PREFIX . "_tags GROUP BY tag ORDER BY count DESC LIMIT 0,60");
```

  
где LIMIT 0,60 — количество тегов извлекаемые из базы данных.  
Ищем в том же файле:  

```
if ($row['count'] >= 40) { 
```

  
и заменяем на:  

```
if ($row['count'] >= 60) { 
```

  
где >= 60— количество тегов выводимые в блоке.
