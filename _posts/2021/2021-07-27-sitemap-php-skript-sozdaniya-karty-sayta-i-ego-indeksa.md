---
title: "sitemap - php скрипт создания карты сайта и его индекса"
date: ""
categories: 
  - "php"
---

Возможности  
\- создает sitemap файл  
\- создает index sitemap файл  
\- автоматически создает новый файл если количество ссылок привешает 50000  
\- эффективная работа с памятью путем настраивания размера буфера  

```
$sitemap->addItem('http://example.com/mylink1');
$sitemap->addItem('http://example.com/mylink2', time());
$sitemap->addItem('http://example.com/mylink3', time(), Sitemap::HOURLY);
$sitemap->addItem('http://example.com/mylink4', time(), Sitemap::DAILY, 0.3);
```

[https://github.com/samdark/sitemap](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3NhbWRhcmsvc2l0ZW1hcA%3D%3D)
