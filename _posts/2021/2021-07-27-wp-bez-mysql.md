---
title: "WP без MySQL"
categories: 
  - "php"
tags: 
  - "mysql"
  - "sqllite"
  - "wp"
---

Плагин [PDO SQLite](https://dev.xfor.top/go/aHR0cDovL3dvcmRwcmVzcy5vcmcvZXh0ZW5kL3BsdWdpbnMvcGRvLWZvci13b3JkcHJlc3Mv) отлично решает вопрос переходом на файловую базу с нативной поддержкой в PHP  
Опять же, бэкап исчерпывается копированием файла.  
  
**Перед запуском установки WP разворачиваем содержимое папки из архива в wp-content и пишем в wp-config.php строчку define(\\'DB\_TYPE\\', \\'sqlite\\');**  
  
Если вылитает ошибка:  

```
Warning: implode() : Invalid arguments passed in /wp-includes/post.php on line 1762
```

  
То, Нужно добавить в функцию escape() в /wp-content/pdo/db.php поддержку массивов:  

```
function escape($string) {if ( is_array($string) ) {foreach ( (array) $string as $k => $v ) {if ( is_array($v) )$string[$k] = $this->escape( $v );else$string[$k] = addslashes( $v );}} else {$string = addslashes( $string );}return $string;}
```
