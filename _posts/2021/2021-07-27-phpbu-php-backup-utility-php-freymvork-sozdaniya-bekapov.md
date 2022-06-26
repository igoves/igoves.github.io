---
title: "phpbu (PHP Backup Utility) - php фреймворк создания бекапов"
date: ""
categories: 
  - "php"
---

Поддерживает различные бд, шифрование, синхронизацию с облаками, и др.  
Пример файла конфигурации  

```
  <?xml version="1.0" encoding="UTF-8"?>
  <phpbu xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:noNamespaceSchemaLocation="http://schema.phpbu.de/3.1/phpbu.xsd"
         verbose="true">
    <backups>
      <backup>
        <!-- source -->
        <source type="mysqldump">
          <option name="databases" value="mydbname"/>
          <option name="user" value="user.name"/>
          <option name="password" value="topsecret"/>
        </source>
        <!-- where should the backup be stored -->
        <target dirname="backup/mysql"
                filename="mysqldump-%Y%m%d-%H%i.sql"
                compress="bzip2"/>
      </backup>
    </backups>
  </phpbu>
```

  
[https://github.com/sebastianfeldmann/phpbu/tree/master](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3NlYmFzdGlhbmZlbGRtYW5uL3BocGJ1L3RyZWUvbWFzdGVy)
