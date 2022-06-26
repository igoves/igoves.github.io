---
title: "Функция генерации тего (ключевых слов) на PHP"
categories: 
  - "php"
---

Выберает из текста вперемешку только слова от 4 символов длинной, генерирует 10($nNumOfTags) тегов.  

```
<?php$nNumTags = 10;$szContent = strip_tags("Это очень умный текст из которого будут делаться теги");$arr_tags = explode(' ', $szContent);shuffle($arr_tags);$nNumOfTags = 0;$str_tag = '';foreach ( $arr_tags as $tvalue ) {    $tvalue = trim($tvalue);    preg_match('/[a-zA-Zа-яА-Я]{4,}/', $tvalue, $t_v);    if ($t_v[0]) {        $str_tag .= $t_v[0].', ';        $nNumOfTags ++;    }    if ($nNumOfTags > $nNumTags)    break;};//$_POST['tags'] = substr($str_tag, 0, strlen($str_tag)-1);$tags = substr($str_tag, 0, strlen($str_tag)-1);echo $tags;//Результат: теги, которого, делаться, умный, текст, очень, будут,
```
