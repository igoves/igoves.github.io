---
title: "Функция склонения слов"
categories: 
  - "php"
---

```
function declension($int, $expressions, $showint = true) {    settype($int, "integer");    $count = $int % 100;    if ($count >= 5 && $count <= 20) {        $result = ($showint? $int." ":"").$expressions['2'];    } else {        $count = $count % 10;        if ($count == 1) {            $result = ($showint? $int." ":"").$expressions['0'];        } elseif ($count >= 2 && $count <= 4) {            $result = ($showint? $int." ":"").$expressions['1'];        } else {            $result = ($showint? $int." ":"").$expressions['2'];        }    }    return $result; }
```

  
  

```
echo 'Ваш заказ на '.price_format($total_price).' '.declension($total_price, array('рубль', 'рубля','рублей'), false).'.';
```

  

В первом мы передаем само число, во втором параметре массив из трех элементов содержащий три вариации написания склоняемого слова, а в третьем параметре задаем флаг отображения числа. Если параметр стоит true, то будет выводится само число в результате работы функции, иначе выведется просто нужное склонение.
