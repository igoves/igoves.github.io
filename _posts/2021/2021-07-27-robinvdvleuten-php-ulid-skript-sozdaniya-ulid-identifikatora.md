---
title: "robinvdvleuten/php-ulid - скрипт создания ULID идентификатора"
categories: 
  - "php"
---

```
use Ulid\\Ulid;

$ulid = Ulid::generate();
print $ulid; // 01B8KYR6G8BC61CE8R6K2T16HY

// Or if you prefer a lowercased output
$ulid = Ulid::generate(true);
print $ulid; // 01b8kyr6g8bc61ce8r6k2t16hy
```

  
[https://github.com/robinvdvleuten/php-ulid](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3JvYmludmR2bGV1dGVuL3BocC11bGlk)
