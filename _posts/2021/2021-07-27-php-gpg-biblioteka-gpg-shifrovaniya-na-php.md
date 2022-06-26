---
title: "php-gpg - библиотека gpg шифрования на php"
categories: 
  - "php"
---

Пример использования  

```
require __DIR__ . '/vendor/autoload.php';
require_once 'libs/GPG.php';

$gpg = new GPG();

// create an instance of a GPG public key object based on ASCII key
$pub_key = new GPG_Public_Key($public_key_ascii);

// using the key, encrypt your plain text using the public key
$encrypted = $gpg->encrypt($pub_key,$plain_text_string);

echo $encrypted;
```

  
[https://github.com/jasonhinkle/php-gpg](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2phc29uaGlua2xlL3BocC1ncGc%3D)
