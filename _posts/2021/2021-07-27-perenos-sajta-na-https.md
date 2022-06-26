---
title: "Перенос сайта на HTTPS"
date: ""
categories: 
  - "php"
tags: 
  - "https"
  - "redirect"
  - "ssl"
---

![Перенос сайта на HTTPS](images/1296900979_31.jpg "Перенос сайта на HTTPS")

  
Стала задача перенести один не хитрый сайт на **https** принудительно.  
  
**HTTPS** (Hypertext Transfer Protocol Secure) — расширение протокола HTTP, поддерживающее шифрование. Данные, передаваемые по протоколу HTTPS, «упаковываются» в криптографический протокол SSL или TLS, тем самым обеспечивается защита этих данных. В отличие от HTTP, для HTTPS по умолчанию используется TCP-порт 443. 
  
**PHP** - в моем случаее не понадобилось, но в Вашем может...  

```
if (!empty($_SERVER['HTTPS']) && ('on' == $_SERVER['HTTPS'])) {        $uri = 'https://';    } else {        $uri = 'http://';    }    $uri .= $_SERVER['HTTP_HOST'];    header('Location: '.$uri.'/');    exit;
```

  
**SSL config апача**  

```
<VirtualHost *:443>  DocumentRoot /usr/var/www/site  ServerName site  SSLEngine on  SSLCipherSuite ALL:!ADH:!EXPORT56:RC4+RSA:+HIGH:+MEDIUM:+LOW:+SSLv2:+EXP:+eNULL  SSLCertificateFile "conf/ssl.crt/server.crt"  SSLCertificateKeyFile "conf/ssl.key/server.key"      <FilesMatch "\\.(cgi|shtml|pl|asp|php)$">        SSLOptions +StdEnvVars    </FilesMatch>     BrowserMatch ".*MSIE.*" nokeepalive ssl-unclean-shutdown downgrade-1.0 force-response-1.0    </VirtualHost>
```

  
**.htaccess** - принудительно редиректим на https  

```
RewriteCond %{SERVER_PORT} !^443$RewriteRule ^(.*)$ https://%{SERVER_NAME}/$1 [L,R]
```
