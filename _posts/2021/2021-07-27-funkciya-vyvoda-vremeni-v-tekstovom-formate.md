---
title: "Функция вывода времени в текстовом формате"
date: ""
categories: 
  - "php"
---

```
function mk_myTime($tonpage) {    if ($tonpage == 0)        return '';    $h = $tonpage / 3600; //часы    if ($pos = strpos($h, '.'))        $h = substr($h,0,$pos);    $timenothour = $tonpage - ($h * 3600);    $m = $timenothour / 60; //минуты    if ($pos = strpos($m, '.'))        $m = substr($m,0,$pos);    $sec = $timenothour - ($m * 60); //секунды    $s = '';    if (intval($h)) $s = declension($h, array("час", "часа", "часов")).' ';    if (intval($m)) $s .= declension($m, array("минуту", "минуты", "минут")).' ';    return $s .= declension($sec, array("секунду", "секунды", "секунд")).' ';}//Функция Из предыдущего поста ПРАВИЛЬНО СКЛОНЯЕМ function declension($int, $expressions, $showint = true) {    settype($int, "integer");    $count = $int % 100;    if ($count >= 5 && $count <= 20) {        $result = ($showint? $int." ":"").$expressions['2'];    } else {        $count = $count % 10;        if ($count == 1) {            $result = ($showint? $int." ":"").$expressions['0'];        } elseif ($count >= 2 && $count <= 4) {            $result = ($showint? $int." ":"").$expressions['1'];        } else {            $result = ($showint? $int." ":"").$expressions['2'];        }    }    return $result; }
```

  
mk\_myTime - эта функция принимает один параметр – время в формате unix\_timestamp.
