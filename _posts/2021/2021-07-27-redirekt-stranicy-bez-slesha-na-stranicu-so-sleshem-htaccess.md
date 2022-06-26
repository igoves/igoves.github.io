---
title: "Редирект страницы без слеша на страницу со слешем .htaccess"
date: ""
categories: 
  - "php"
---

```
RewriteCond %{REQUEST_FILENAME} !-fRewriteCond %{REQUEST_FILENAME} !-dRewriteRule ^([^.]+)(?<!/)$ /$1/ [R=301,L]
```
