---
title: "Функция создания цветовой палитры на PHP"
categories: 
  - "php"
tags: 
  - "gd"
  - "palette"
  - "php"
  - "palitra"
  - "funkciya"
  - "cveta"
---

![Функция создания цветовой палитры на PHP](images/1290200843_untitled-1.jpg "Функция создания цветовой палитры на PHP")  

```
<?php function colorPalette($imageFile, $numColors, $granularity = 5) {    $granularity = max(1, abs((int)$granularity));    $colors = array();    $size = @getimagesize($imageFile);    if($size === false)    {       user_error("Unable to get image size data");       return false;    }    $img = @imagecreatefromjpeg($imageFile);    if(!$img)    {       user_error("Unable to open image file");       return false;    }    for($x = 0; $x < $size[0]; $x += $granularity)    {       for($y = 0; $y < $size[1]; $y += $granularity)       {          $thisColor = imagecolorat($img, $x, $y);          $rgb = imagecolorsforindex($img, $thisColor);          $red = round(round(($rgb['red'] / 0x33)) * 0x33);          $green = round(round(($rgb['green'] / 0x33)) * 0x33);          $blue = round(round(($rgb['blue'] / 0x33)) * 0x33);          $thisRGB = sprintf('%02X%02X%02X', $red, $green, $blue);          if(array_key_exists($thisRGB, $colors))          {             $colors[$thisRGB]++;          }          else          {             $colors[$thisRGB] = 1;          }       }    }    arsort($colors);    return array_slice(array_keys($colors), 0, $numColors); } ?><div align="center"><img src="58.jpg" alt="58.jpg"/><br/><br/></div><?php// пример использования: $palette = colorPalette('58.jpg', 10, 5); echo "<table align='center'>\\n"; foreach($palette as $color) {    echo "<tr><td style='background-color:#$color;width:2em;'>&nbsp;</td><td>#$color</td></tr>\\n"; } echo "</table>\\n";
```

Обязательно наличие модуля GD  
  
[СМОТРЕТЬ ДЕМО](https://dev.xfor.top/uploads/files/demo/028/palette.php)
