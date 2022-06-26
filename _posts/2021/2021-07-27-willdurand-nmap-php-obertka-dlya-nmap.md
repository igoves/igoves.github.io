---
title: "willdurand/nmap - php обертка для nmap"
date: ""
categories: 
  - "php"
---

Пример

```
$nmap
    ->enableOsDetection()
    ->scan([ 'williamdurand.fr' ]);

$nmap
    ->enableServiceInfo()
    ->scan([ 'williamdurand.fr' ]);

// Fluent interface!
$nmap
    ->enableOsDetection()
    ->enableServiceInfo()
    ->scan([ 'williamdurand.fr' ]);
```

  
[https://github.com/willdurand/nmap](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3dpbGxkdXJhbmQvbm1hcA%3D%3D)
