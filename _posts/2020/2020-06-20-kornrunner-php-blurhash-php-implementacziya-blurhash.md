---
title: "kornrunner/php-blurhash - php имплементация blurhash"
date: "2020-06-20"
categories: 
  - "php"
tags: 
  - "blurhash"
  - "hash"
---

```
<?php

require_once 'vendor/autoload.php';

use kornrunner\Blurhash\Blurhash;

$file  = 'test/data/img1.jpg';
$image = imagecreatefromstring(file_get_contents($file));
$width = imagesx($image);
$height = imagesy($image);

$pixels = [];
for ($y = 0; $y < $height; ++$y) {
    $row = [];
    for ($x = 0; $x < $width; ++$x) {
        $index = imagecolorat($image, $x, $y);
        $colors = imagecolorsforindex($image, $index);

        $row[] = [$colors['red'], $colors['green'], $colors['blue']];
    }
    $pixels[] = $row;
}

$components_x = 4;
$components_y = 3;
$blurhash = Blurhash::encode($pixels, $components_x, $components_y);
// LEHV9uae2yk8pyo0adR*.7kCMdnj
```

[https://github.com/kornrunner/php-blurhash](https://github.com/kornrunner/php-blurhash)
