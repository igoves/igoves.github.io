---
title: "Выставляем свои robots.txt в .htaccess для субдоменов"
categories: 
  - "note"
---

А вот так

```
<IfModule mod_rewrite.c>
    RewriteEngine on
    RewriteCond %{HTTP_HOST} ^dev\\.site\\.com$
    RewriteRule ^robots\\.txt$ robots-dev.txt
</IfModule>
```

  
И создаем файл robots-dev.txt с нужным нам содержанием, например:  

User-agent: \*  
Disallow: /
