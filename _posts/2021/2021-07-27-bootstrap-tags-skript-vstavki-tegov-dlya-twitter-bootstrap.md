---
title: "bootstrap-tags - скрипт вставки тегов для twitter bootstrap"
date: ""
categories: 
  - "js"
---

![bootstrap-tags - скрипт вставки тегов для twitter bootstrap](images/1433585324_untitled-2.png "bootstrap-tags - скрипт вставки тегов для twitter bootstrap")

  
Поддержка Bootstrap 2.3.2 and 3+, фильтров, авто заполнения, Bootstrap Popovers, исключений, Placeholder, разных стилей, возможность расширить пользовательскими функциями.  
  
Пример использования

```
<!-- include bootstrap tags js, css files -->
<script src='path/to/bootstrap-tags/dist/js/bootstrap-tags.min.js'></script>
<link rel="stylesheet" type="text/css" href="path/to/bootstrap-tags/dist/css/bootstrap-tags.css" />

<div id="my-tag-list" class="tag-list"></div>
<script>
    $(function() {
        // If using Bootstrap 2, be sure to include:
        // Tags.bootstrapVersion = "2";
        $('#my-tag-list').tags({
            tagData:["boilerplate", "tags"],
            suggestions:["basic", "suggestions"],
            excludeList:["not", "these", "words"]
        });
    });
</script>
```

  
  
[https://github.com/maxwells/bootstrap-tags](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL21heHdlbGxzL2Jvb3RzdHJhcC10YWdz)
