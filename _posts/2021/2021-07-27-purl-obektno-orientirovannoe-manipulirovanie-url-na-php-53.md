---
title: "Purl - обьектно ориентированное манипулирование URL на PHP 5.3+"
date: ""
categories: 
  - "php"
---

```
$url = \\Purl\\Url::parse('http://jwage.com')    ->set('scheme', 'https')    ->set('port', '443')    ->set('user', 'jwage')    ->set('pass', 'password')    ->set('path', 'about/me')    ->set('query', 'param1=value1&param2=value2')    ->set('fragment', 'about/me?param1=value1&param2=value2');echo $url->getUrl(); // https://jwage:password@jwage.com:443/about/me?param1=value1&param2=value2#about/me?param1=value1&param2=value2// $url->path becomes instanceof Purl\\Path// $url->query becomes instanceof Purl\\Query// $url->fragment becomes instanceof Purl\\Fragment
```

  
[https://github.com/jwage/purl](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2p3YWdlL3B1cmw%3D)
