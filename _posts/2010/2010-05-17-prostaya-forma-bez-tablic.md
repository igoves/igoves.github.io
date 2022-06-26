---
title: "Простая форма без таблиц"
date: "2010-05-17"
categories: 
  - "css"
tags: 
  - "bez-tablic"
  - "forma"
---

Очень часто сталкиваюсь с созданием форм. И сейчас я приведу как просто обойти таблицы и даже блочную верстку, но при этом получить правильную ровную форму.

```
<form>
<label for="name">Name</label>
<input id="name" name="name"><br>
<label for="address">Address</label>
<input id="address" name="address"><br>
<label for="city">City</label>
<input id="city" name="city"><br>
</form>
```

!семантично

```
label,input {
display: block;
width: 150px;
float: left;
margin-bottom: 10px;
}
label {
text-align: right;
width: 75px;
padding-right: 20px;
}
br {
clear: left;
}
```

[demo](https://dev.xfor.top/uploads/files/demo/005/index.html)
