---
title: "ausi/slug-generator - slug генератор на PHP"
categories: 
  - "php"
---

```
<?php
use Ausi\\SlugGenerator\\SlugGenerator;

$generator = new SlugGenerator;

$generator->generate('Hello W?rld!');  // Output: hello-world
$generator->generate('????????');      // Output: kalemera
$generator->generate('фильм');         // Output: film
$generator->generate('???');         // Output: fu-shi-shan
$generator->generate('??');           // Output: guo-yu

// Different valid character set, a specified locale and a delimiter
$generator = new SlugGenerator((new SlugOptions)
    ->setValidChars('a-zA-Z0-9')
    ->setLocale('de')
    ->setDelimiter('_')
);
$generator->generate('?pfel und B?ume');  // Aepfel_und_Baeume
```

  
[https://github.com/ausi/slug-generator](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2F1c2kvc2x1Zy1nZW5lcmF0b3I%3D)
