---
title: "PHLAK/Twine - php скрипт для манипуляций с строкой"
categories: 
  - "php"
---

```
$string = new Twine\\Str('john pinkerton');
$string->substring(5, 4); // Returns 'pink'
```

```
$string = new Twine\\Str('john pinkerton');
$string->truncate(12); // Returns 'john pink...'
$string->truncate(10, '~'); // Returns 'john pink~'
$string->truncate(8); // Returns 'john...'
```

И много других методов  
[https://github.com/PHLAK/Twine](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL1BITEFLL1R3aW5l)
