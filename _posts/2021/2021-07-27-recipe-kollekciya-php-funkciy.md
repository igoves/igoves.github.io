---
title: "Recipe - коллекция пхп функций"
categories: 
  - "php"
---

Favicon, QRcode, File extension, Gravatar, Creating Link Tags, Validate email address, Validate URL, RSS Reader, Object to Array, Array to Object, Array to String, HEX to RGB, RGB to HEX, Generate Random Password, Simple Encode, Simple Decode, Generate Server Specific Hash, Detect HTTPS, Detect AJAX, Check if number is odd, Check if number is even, Get Current URL, Get Client IP, Detect Mobile, Get Browser, Get Client Location, Number To Word conversion, Seconds To Text, Minutes To Text, Hours To Text, Shorten String, CURL, Shorten URL, Get Alexa Rank, Get Google PageRank, Get Tiny URL, Get Keyword Suggestions From Google, WIKI Search, Notification, Auto Embed, Make Clickable Links, :wrench: Debug, Get Referer :new:, Compress Page  
  
Пример получения favicon

```
$favIcon = \\ngfw\\Recipe::getFavicon("http://youtube.com/");

echo $favIcon;
// outputs: <img src="http://www.google.com/s2/favicons?domain=youtube.com/"  />
```

  
[https://github.com/ngfw/Recipe](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL25nZncvUmVjaXBl)
