---
title: "Плейсхолдеры и ХТМЛ5"
categories: 
  - "xhtml"
tags: 
  - "html5"
  - "placeholder"
---

![Плейсхолдеры и ХТМЛ5](images/1307880375_27.jpg "Плейсхолдеры и ХТМЛ5")

  
Не так давно написал: [Очистка поля input при фокусе на jQuery](https://dev.xfor.top/602-ochistka-polya-input-pri-fokuse-na-jquery.html)  
Оказывается в ХТМЛ5 есть плейсхолдер и выглядит это приблизительно так:  
ХТМЛ  

```
<h1 class="project-name">    <a href="http://unwrongest.com/projects/defaultvalue">Unwrongest - Jquery Defaultvalue</a></h1><input id="username" placeholder="Enter a username..." type="text" /><input id="password" placeholder="Enter a password..." type="password" /><textarea id="description" placeholder="Describe yourself..."></textarea>
```

  
ЦСС  

```
body { background: #0D1114; }.project-name a { padding: 0; color: #3cf; text-transform: uppercase; font: bold 13px/30px 'Arial', 'sans-serif'; }input,textarea{ padding: 10px; width: 300px; font-weight: bold; font-family: Arial, 'sans-serif'; margin-bottom: 10px; font-size: 13px; border: none; clear: both; float: left; }.empty { color: #999; }
```

  
ЯВА  

```
$('#username, #password, #description').defaultValue();
```

  
И вот [ДЕМО](https://dev.xfor.top/go/aHR0cDovL2pzZmlkZGxlLm5ldC9qYW5qYXJmYWxrL3JucVAzLw%3D%3D).
