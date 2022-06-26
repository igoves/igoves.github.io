---
title: "Обрезание текста до слова (функция php)"
date: ""
categories: 
  - "php"
tags: 
  - "truncate"
---

![Обрезание текста до слова (функция php)](images/1301938193_70.jpg "Обрезание текста до слова (функция php)")

  

```
function myTruncate($string, $limit, $break=" ", $pad="..."){  if(strlen($string) <= $limit) return $string;  $string = substr($string, 0, $limit);  if(false !== ($breakpoint = strrpos($string, $break))) {    $string = substr($string, 0, $breakpoint);  }  return $string . $pad;}$text = myTruncate($text, 115);
```
