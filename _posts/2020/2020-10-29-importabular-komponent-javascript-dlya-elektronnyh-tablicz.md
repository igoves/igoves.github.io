---
title: "importabular - компонент javascript для электронных таблиц"
date: "2020-10-29"
categories: 
  - "js"
tags: 
  - "excel"
  - "spreadsheet"
---

```
import Importabular from 'importabular'
const sheet=new Importabular({
  node:document.getElementById('editorNode'),
})
sheet.setData([['Content of A1','of A2','A3'], ['B1','B2','etc.']])
```

[https://github.com/renanlecaro/importabular](https://github.com/renanlecaro/importabular)
