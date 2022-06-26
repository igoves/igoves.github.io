---
title: "lorisleiva/laravel-search-string - создает запросы к базе данных на основе одной уникальной строки"
date: ""
categories: 
  - "php"
tags: 
  - "laravel"
  - "search"
---

```
Article::usingSearchString('title:"My blog article" or not published sort:-created_at');

// Так выглядит запрос без скрипта:
Article::where('title', 'My blog article')
       ->orWhere('published', false)
       ->orderBy('created_at', 'desc');
```

  

```
Invoice::usingSearchString('John and status in (Paid,Archived) limit:10 from:10');

// Так выглядит запрос без скрипта:
Invoice::where(function ($query) {
           $query->where('customer', 'like', '%John%')
               ->orWhere('description', 'like', '%John%');
       })
       ->whereIn('status', ['Paid', 'Archived'])
       ->limit(10)
       ->offset(10);
```

  
[https://github.com/lorisleiva/laravel-search-string](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2xvcmlzbGVpdmEvbGFyYXZlbC1zZWFyY2gtc3RyaW5n)
