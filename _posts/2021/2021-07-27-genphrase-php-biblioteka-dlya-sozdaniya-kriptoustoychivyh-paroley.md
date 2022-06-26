---
title: "GenPhrase - пхп библиотека для создания криптоустойчивых паролей"
categories: 
  - "php"
---

```
<?php
require '/path/to/library/GenPhrase/Loader.php';
$loader = new GenPhrase\\Loader();
$loader->register();
$gen = new GenPhrase\\Password();
// Generate a passphrase using english words and (at least) 50 bits of entropy.
$gen->generate();
```

  
[https://github.com/timoh6/GenPhrase](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3RpbW9oNi9HZW5QaHJhc2U%3D)
