---
title: "Decoda - парсер BBCode на PHP"
categories: 
  - "php"
---

**Возможности**  
\- Парсит код в валидную (X)HTML разметку  
\- Автоматом делает ссылки кликабельными  
\- Фильтры для разбора разметки  
\- Хуки: цензор, смайлы, конвертация в кликабельные ссылки  
\- Поддержка локализации  
\- Поддерживает широкий спектр тегов  
\- Поддержка иерархичности  
\- Исправление вложеных не верных тегов  
\- Самостоятельно закрывающие теги  
\- Журналы ошибок для проверки  
и другое.  
  

```
<?php $string = '[list]
[li]Lorem ipsum dolor sit amet, consectetuer adipiscing elit.[/li]
[li]Aliquam laoreet pulvinar sem. Aenean at odio.[/li]
[li]Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Donec elit.[/li]
[li]Fusce eget enim. Nullam tellus felis, sodales nec, sodales ac, commodo eu, ante.[/li]
[li]Curabitur tincidunt, lacus eget iaculis tincidunt.[/li]
[li]Curabitur sed tellus. Donec id dolor.[/li]
[/list]';
```

  
**Фильтры и поддерживаемые теги**  
Default - b, i, u, s, sup, sub, br, hr, abbr, time  
Block - align, float, hide, alert, note, div, spoiler, left, right, center, justify  
Code - code, source, var  
Email - email, mail  
Image - image, img  
List - list, olist, ol, ul, li, \*  
Quote - quote  
Text - font, size, color, h1-h6  
Url - url, link  
Video - video, youtube, vimeo, veoh, liveleak, dailymotion, myspace, wegame, collegehumor  
Table - table, thead, tbody, tfoot, tr, td, th, row, col  
  
[https://github.com/milesj/decoda](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL21pbGVzai9kZWNvZGE%3D)
