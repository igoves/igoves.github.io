---
title: "Полезные linux команды для работы с php проектами"
categories: 
  - "note"
---

Найти все PHP файлы в текущей директории

```
$ find . -type f -name "*.php"
./index.php
./vendor/autoload.php
```

  
Вы так же можете использовать любой другой формат

```
$ find . -type f -name "*.twig"
./test.twig
 
$ find . -type f -name "*.json"
./composer.json
```

  
Проверить синтаксис всех файлов PHP в текущей директории

```
$ find . -type f -name "*.php" -exec php -l {} \\;
No syntax errors detected in ./index.php
No syntax errors detected in ./vendor/autoload.php
```

  
Узнать размер директорий

```
$ du -h -d 2 vendor
 56K    vendor/composer
496K    vendor/symfony/config
1.2M    vendor/symfony/console
...
```

  
Найти подозрительные php файлы ( присутствует eval(base64\_decode) )

```
$ find . -type f -name "*.php" -exec grep --with-filename "eval(\\|exec(\\|base64_decode(" {} \\;
./virus.php: eval(base64_decode($_GET['a']));
```

  
Найти все файлы использующие абстрактные классы

```
[$ find . -type f -name "*.php" -exec grep --with-filename -c "^abstract class " {} \\; | grep ":[^0]"
./vendor/twig/twig/test/Twig/Tests/Profiler/Dumper/AbstractTest.php:1
./vendor/twig/twig/lib/Twig/TokenParser.php:1
.../code]
Найти пустые файлы[code]$ find . -type f -empty
./test.txt
```

  
Получить список файлов которые в настоящее время открыт как PHP процесс

```
$ php test.php &
[2] 9525
 
$ ps aux|grep "test.php"
root      9525  0.1  2.0 161404 10736 pts/0    S    11:07   0:00 php test.
```

```
$ ls -l /proc/9525/fd
total 0
lrwx------ 1 root root 64 Apr 23 11:07 0 -> /dev/pts/0
lrwx------ 1 root root 64 Apr 23 11:07 1 -> /dev/pts/0
lrwx------ 1 root root 64 Apr 23 11:07 2 -> /dev/pts/0
lr-x------ 1 root root 64 Apr 23 11:07 3 -> /proc/9525/auxv
l-wx------ 1 root root 64 Apr 23 11:07 4 -> /test.txt
```

```
$ ls -l /proc/9580/exe
lrwxrwxrwx 1 root root 0 Apr 23 11:11 /proc/9525/exe -> /usr/local/php54/bin/php
 
$ /usr/local/php54/bin/php -v
PHP 5.4.5 (cli) (built: Jul 26 2012 15:17:07)
```
