---
title: "php-ftp-client - гибкий FTP и SSL-FTP клиент на php"
date: ""
categories: 
  - "php"
---

```
$ftp = new \\FtpClient\\FtpClient();
$ftp->connect($host);
$ftp->login($login, $password);
// upload with the BINARY mode
$ftp->putAll($source_directory, $target_directory);
```

  
[https://github.com/Nicolab/php-ftp-client](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL05pY29sYWIvcGhwLWZ0cC1jbGllbnQ%3D)
