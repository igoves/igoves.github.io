---
title: "benhowdle89/grade - библиотека JS создает градиенты, сгенерированные из 2 доминирующих цветов"
date: "2020-07-21"
categories: 
  - "js"
tags: 
  - "colors"
  - "gradient"
---

![](https://res.cloudinary.com/xfor/images/v1597343920/bez-imeni-1-5/bez-imeni-1-5.jpg?_i=AA)

```
<script src="path/to/grade.js"></script>
<script type="text/javascript">
    window.addEventListener('load', function(){
        /*
            A NodeList of all your image containers (Or a single Node).
            The library will locate an <img /> within each
            container to create the gradient from.
         */
        Grade(document.querySelectorAll('.gradient-wrap'))
    })
</script>
```

[https://github.com/benhowdle89/grade](https://github.com/benhowdle89/grade)
