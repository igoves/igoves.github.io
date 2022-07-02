---
title: "taffydb - база данных на js"
date: "2021-03-01"
categories: 
  - "js"
tags: 
  - "clientside"
  - "db"
---

```
var friends = TAFFY([
	{"id":1,"gender":"M","first":"John","last":"Smith","city":"Seattle, WA","status":"Active"},
	{"id":2,"gender":"F","first":"Kelly","last":"Ruth","city":"Dallas, TX","status":"Active"},
	{"id":3,"gender":"M","first":"Jeff","last":"Stevenson","city":"Washington, D.C.","status":"Active"},
	{"id":4,"gender":"F","first":"Jennifer","last":"Gill","city":"Seattle, WA","status":"Active"}	
]);
```

Пример выборки данных

```
// Kelly's record
var kelly = friends({id:2}).first();

// Kelly's last name
var kellyslastname = kelly.last;

// Get an array of record ids
var cities = friends().select("id");

// Get an array of distinct cities
var cities = friends().distinct("city");

// Apply a function to all the male friends
friends({gender:"M"}).each(function (r) {
   alert(r.name + "!");
});
```

[https://taffydb.com/](https://taffydb.com/)
