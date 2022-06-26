---
title: "Как писать ошибки выполнения скриптов в файл"
categories: 
  - "php"
---

**Способ 1 — изменить php.ini:**  
log\_errors = On  
error\_log = /var/log/php\_errors.log  
  
**Способ 2 — добавить в .htaccess:**  
php\_value log\_errors \\"On\\"  
php\_value error\_log /var/log/php\_errors.log  
  
**Способ 3 — добавить в самое начало php скрипта:**  
ini\_set(\\'log\_errors\\', \\'On\\');  
ini\_set(\\'error\_log\\', \\'/var/log/php\_errors.log\\');
