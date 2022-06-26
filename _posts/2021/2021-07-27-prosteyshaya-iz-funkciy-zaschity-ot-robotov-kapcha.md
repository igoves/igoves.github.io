---
title: "Простейшая из функций защиты от роботов, капча"
categories: 
  - "php"
tags: 
  - "cap4a"
  - "captcha"
  - "php"
---

![Простейшая из функций защиты от роботов, капча](images/1313500167_55.jpg "Простейшая из функций защиты от роботов, капча")

  

```
<?php function generate_code () {  srand (time());  $num=round(rand(1,4));  $valid=0;  echo "$num-й код из чисел: ";  for ($i=1; $i<5; $i++) {   $n=round(rand(1000,9999));   if ($i==$num) $valid=$n;   echo "$n";   if ($i<4) echo ", ";   else echo '<br/>';  }  $valid1=md5($valid);  echo "<input type=text name=code size=4 maxlength=4 value=\\"\\"><input type=hidden name=valid value=\\"$valid1\\">";}//Вызовecho generate_code();//Проверкаif ( empty($_POST['code']) or empty($_POST['valid']) or md5($_POST['code'])!=$_POST['valid'] )    die('Капчу запили блеать!');
```

\+ Не использует сессии
