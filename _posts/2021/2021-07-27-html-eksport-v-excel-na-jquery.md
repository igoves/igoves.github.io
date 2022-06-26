---
title: "HTML експорт в EXCEL на jQuery"
date: ""
categories: 
  - "js"
---

![HTML експорт в EXCEL на jQuery](images/1390672349_html-export-to-excel.png "HTML експорт в EXCEL на jQuery")

  

```
$("#export").click(function (e) {    window.open('data:application/vnd.ms-excel,' + encodeURIComponent($('#tableHolder').html()));    e.preventDefault();});
```

  
[Демо с CSS](https://dev.xfor.top/go/aHR0cDovL2pzZmlkZGxlLm5ldC9sZXNzb244L3dWZWpQL3Nob3cv) | [Демо без CSS](https://dev.xfor.top/go/aHR0cDovL2pzZmlkZGxlLm5ldC9sZXNzb244L2pXQUo3L3Nob3cv)
