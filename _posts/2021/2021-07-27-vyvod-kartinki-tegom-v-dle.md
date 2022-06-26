---
title: "Вывод картинки тегом в DLE"
date: ""
categories: 
  - "php"
tags: 
  - "dle"
---

В результате вы получаете ссылку на изображение которое присутствует в новости.  
Имеет единственный минус - картинка в новости обязательна!  
  
**engine/modules/show.short.php**  
Найдем в нем:  

```
        $tpl->compile( 'content' );
```

  
И перед этим вставляем:  

```
$shortnews = $row['short_story'];preg_match_all( '#<img[^>]*\\\\ssrc=(\\'|")(.*?)\\\\1.*?>#i',$shortnews,$total);foreach( $total[2] as $shortnews );$tpl->set( '{imgbla}',$shortnews);
```

  
В шаблон **shorpstory.tpl** вставлем {imgbla}  
В результате вы получите ссылку на изображение.  

Автор: Пряник
