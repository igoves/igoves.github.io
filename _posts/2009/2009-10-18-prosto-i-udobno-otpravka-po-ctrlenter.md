---
title: "Просто и удобно, отправка по Ctrl+Enter"
date: "2009-10-18"
categories: 
  - "js"
---

Собственно код:

```
<script type="text/javascript">
function ctrlEnter(event, formElem)
    {
    if((event.ctrlKey) && ((event.keyCode == 0xA)||(event.keyCode == 0xD)))
        {
        formElem.submit.click();
        }
    }
</script>
<form action="send.php" method="post" onkeypress="ctrlEnter(event, this);">...</form>
```

зы: Сменил хостера (ну и домен самосабой кто не заметил) [сайт](https://dev.xfor.top) должен на порядок быстрей грузиться.
