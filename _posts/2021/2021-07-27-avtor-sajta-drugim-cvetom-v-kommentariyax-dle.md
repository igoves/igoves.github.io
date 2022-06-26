---
title: "Автор сайта другим цветом в комментариях DLE"
date: ""
categories: 
  - "css"
tags: 
  - "kommentarii"
  - "podsvetka"
---

Захотелось мне выделять свои комментарии от других.  
Например вот как здесь: [https://dev.xfor.top/273-100-multiyazych...ne.html#comment](https://dev.xfor.top/273-100-multiyazychnost-datalife-engine.html#comment)  
Похожее что-то находил когда-то в нете.  
Как сделал это я:  
**/engine/classes/comments.class.php** перед  

```
if( $row['is_register'] and $row['icq'] ) $tpl->set( '{icq}', stripslashes( $row['icq'] ) );
```

  
вставить  

```
if( $row['is_register'] ) $tpl->set( '{color}', 'qwerty1' );else $tpl->set( '{color}', 'qwerty2' );
```

  
И не забыть вставить в comments.tpl - {color}  
То есть все кто зарегистрированы на сайте будут подсвечиваться классом **qwerty1**, все остальные **qwerty2**, а так как регистрация запрещена здесь, то подсвечивается только мои. Задача выполнена.
