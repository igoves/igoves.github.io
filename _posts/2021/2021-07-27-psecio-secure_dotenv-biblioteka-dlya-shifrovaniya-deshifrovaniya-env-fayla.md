---
title: "psecio/secure_dotenv - библиотека для шифрования/дешифрования .env файла"
date: ""
categories: 
  - "php"
---

```
<?php
require_once __DIR__.'/vendor/autoload.php';

$keyfile = __DIR__.'/keyfile';
$envFile = __DIR__.'/.env';

$d = new \\Psecio\\SecureDotenv\\Parser($keyfile, $envFile);

// The contents here is the set of all decrypted values fron the .env
print_r($d->getContent());
?>
```

  
[https://github.com/psecio/secure\_dotenv](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3BzZWNpby9zZWN1cmVfZG90ZW52)
