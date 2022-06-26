---
title: "ul li по центру"
date: ""
categories: 
  - "css"
---

Извечный вопрос как сделать меню ul li по центру, способов есть несколько, вот один из них:  

```
    <ul>      <li>test</li>      <li>test</li>      <li>test</li>      <li>test</li>      <li>test</li>    </ul>
```

  

```
ul {        width:100%;        background:red;        height:20px;        text-align:center;}li {        display:inline-block;        *display:inline; /*IE7*/        *zoom:1; /*IE7*/        background:blue;        color:white;        margin-right:10px;}
```

  
[http://jsfiddle.net/3Ezx2/3/](https://dev.xfor.top/go/aHR0cDovL2pzZmlkZGxlLm5ldC8zRXp4Mi8zLw%3D%3D)
