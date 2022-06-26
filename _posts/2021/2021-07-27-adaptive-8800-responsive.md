---
title: "Adaptive &#8800; Responsive"
categories: 
  - "css"
---

**Responsive**

```
.container {	width: 90%;	max-width: 1200px;	margin: 0 auto;}
```

  
**Adaptive**

```
.container {    width: 700px;}@media only screen and (max-width: 767px) and (min-width: 480px) {    .container {        width: 420px;    }}@media only screen and (max-width: 767px) {    .container {        width: 300px;    }}
```
