---
title: "Стили посещенных ссылок"
categories: 
  - "css"
tags: 
  - "visited"
  - "linki"
  - "poseshchennye"
  - "ssylki"
  - "stili"
---

Зачеркнутая ссылка:  

```
a:visited { text-decoration: line-through; }
```

  
С добавлением картинки:  

```
a:visited { padding-right: 12px; background: url(visitedLink.gif) no-repeat 100% 50%; }
```

  
С добавлением картинки и подмены картинки при наведении на посещенную ссылку:  

```
a:visited { padding-right: 12px; background: url(visitedLink.gif) no-repeat 100% 50%; color: #aaa; text-decoration: none; }a:visited:hover { background-image: url(visitedHoverLink.gif); color: #f00; }
```

  
  
**Дальше идут методы с использование псевдоэлементов**  
  
К посещенной ссылке добавляется текст:  

```
a:visited:before { content: "(you've visited this link already) "; }
```

  
При наведении на посещенную ссылку появляется новый текст:  

```
a:visited:after { content: " (ok)"; font-size: 60%; text-transform: uppercase; color: #777; }a:visited:hover:after { content: " (hey! you've already been there!)"; font-size: 80%; text-transform: uppercase; color: #f00; }
```

  
  

[ДЕМО](https://dev.xfor.top/uploads/files/demo/021/links_visited.html)
