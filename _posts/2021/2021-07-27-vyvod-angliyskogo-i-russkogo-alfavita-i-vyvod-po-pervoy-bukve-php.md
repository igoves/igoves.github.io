---
title: "Вывод английского и русского алфавита и вывод по первой букве php"
date: ""
categories: 
  - "php"
---

**Английский алфавит**  

```
foreach(range('A', 'Z') as $letter) {    echo $letter;}
```

  
**Русский алфавит**  

```
foreach (range(chr(0xC0), chr(0xDF)) as $b) {	echo iconv('CP1251', 'UTF-8', $b);}
```

  
**Вывод по первой букве**  

```
SELECT Author FROM Message190 WHERE LCASE(LEFT(Author,1))='а'
```
