---
title: "phan - статический анализатор для PHP"
date: ""
categories: 
  - "php"
---

Выводит вот такой вот отчет:

```
test1.php:191 UndefError call to undefined function get_real_size()
test1.php:232 UndefError static call to undeclared class core\\session\\manager
test1.php:386 UndefError Trying to instantiate undeclared class lang_installer
test2.php:4 TypeError arg#1(arg) is object but escapeshellarg() takes string
test2.php:4 TypeError arg#1(msg) is int but logmsg() takes string defined at sth.php:5
test2.php:4 TypeError arg#2(level) is string but logmsg() takes int defined at sth.php:5
test3.php:11 TypeError arg#1(number) is string but number_format() takes float
test3.php:12 TypeError arg#1(string) is int but htmlspecialchars() takes string
test3.php:13 TypeError arg#1(str) is int but md5() takes string
test3.php:14 TypeError arg#1(separator) is int but explode() takes string
test3.php:14 TypeError arg#2(str) is int but explode() takes string
```

  
**Требует PHP7 и расширение php-ast** =)  
[https://github.com/etsy/phan](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2V0c3kvcGhhbg%3D%3D)
