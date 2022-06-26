---
title: "Делаем форму как на картинке jQuery"
date: ""
categories: 
  - "js"
tags: 
  - "clone"
  - "clone-input"
  - "form"
---

![Делаем форму как на картинке jQuery](images/1333794404_untitled-2.jpg "Делаем форму как на картинке jQuery")

  
**HTML**  

```
<form method="post" action="clonesubmit.php">   <p class="clone"> <input type="text" name="hobby[]" class='input'/></p>   <p><a href="#" class="add" rel=".clone">Add More</a></p>   <input type="submit" value=" Submit " />   </form>
```

  
Подключаем плагин relCopy.js [http://www.andresvidal.com/labs/relcopy.html](https://dev.xfor.top/go/aHR0cDovL3d3dy5hbmRyZXN2aWRhbC5jb20vbGFicy9yZWxjb3B5Lmh0bWw%3D)  
  
Добавляем js который добавляет линк на удаление нового поля:  

```
$(function(){  var removeLink = ' <a class="remove" href="#" onclick="$(this).parent().slideUp(function(){ $(this).remove() }); return false">remove</a>';$('a.add').relCopy({ append: removeLink});    });
```

  
  
Ну и на **clonesubmit.php** вешаем обработчик hobby\[\]
