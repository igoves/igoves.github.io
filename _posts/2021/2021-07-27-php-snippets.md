---
title: "php snippets"
categories: 
  - "php"
---

Вывести исходный код страницы  

```
$lines = file('http://google.com/');foreach ($lines as $line_num => $line) { 	echo "Line #<b>{$line_num}</b> : " . htmlspecialchars($line) . "\\n";}
```

  
  
Определение защищенного https подключения  

```
if ($_SERVER['HTTPS'] != "on") { 	echo "This is not HTTPS";}else{	echo "This is HTTPS";}
```

  
  
Определить доминантный цвет картинки  

```
$i = imagecreatefromjpeg("image.jpg");for ($x=0;$x<imagesx($i);$x++) {    for ($y=0;$y<imagesy($i);$y++) {        $rgb = imagecolorat($i,$x,$y);        $r   = ($rgb >> 16) & 0xFF;        $g   = ($rgb >>  & 0xFF;        $b   = $rgb & 0xFF;        $rTotal += $r;        $gTotal += $g;        $bTotal += $b;        $total++;    }}$rAverage = round($rTotal/$total);$gAverage = round($gTotal/$total);$bAverage = round($bTotal/$total);
```
