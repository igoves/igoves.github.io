---
title: "php-gif - скрипт создания gif-ок"
categories: 
  - "php"
---

![php-gif - скрипт создания gif-ок](https://camo.githubusercontent.com/a092007c32f97456d7238c144918135bfc4f81bc/687474703a2f2f6f6e6c792d6d656469612e6e6c2f6769662f6769662e706870 "php-gif - скрипт создания gif-ок")

  

```
// Caching disable headers
header("Cache-Control: no-store, no-cache, must-revalidate, max-age=0");
header("Cache-Control: post-check=0, pre-check=0", false);
header("Pragma: no-cache");

// Output as a GIF image
header ('Content-type:image/gif');

// Include the GIFGenerator class
include('GIFGenerator.class.php');

// Initialize a new GIFGenerator object
$gif = new GIFGenerator();

// Create a multidimensional array with all the image frames
$imageFrames = array(
    'repeat' => false,
    'frames' => array(
        array(
            'image' => './images/newyear.jpg',
            'text' => array(
                array(
                    'text' => 'Hello GIF frame 1',
                    'font-color' => '#000',
                    'x-position' => 140,
                    'y-position' => 138
                )
            ),
            'delay' => 100
        ),
    )
);

echo $gif->generate($imageFrames);
```

  
[https://github.com/ErikvdVen/php-gif](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL0VyaWt2ZFZlbi9waHAtZ2lm)
