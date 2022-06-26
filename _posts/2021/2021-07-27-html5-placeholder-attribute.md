---
title: "HTML5 Placeholder Attribute"
categories: 
  - "xhtml"
---

![HTML5 Placeholder Attribute](images/1333795022_51.jpg "HTML5 Placeholder Attribute")

  
Ранее я уже писал о плейсхолдерах. **Нормальные браузеры** поддерживают

```
<input type='text' name='email' placeholder='Email Address'/>
```

. Вот костыль на jquery который решает проблему для недобраузеров:  

```
<script>    // placeholder polyfill    $(document).ready(function(){        function add() {            if($(this).val() == ''){                $(this).val($(this).attr('placeholder')).addClass('placeholder');            }        }        function remove() {            if($(this).val() == $(this).attr('placeholder')){                $(this).val('').removeClass('placeholder');            }        }        // Create a dummy element for feature detection        if (!('placeholder' in $('<input>')[0])) {            // Select the elements that have a placeholder attribute            $('input[placeholder], textarea[placeholder]').blur(add).focus(remove).each(add);        // Remove the placeholder text before the form is submitted            $('form').submit(function(){                $(this).find('input[placeholder], textarea[placeholder]').each(remove);            });        }    });</script>
```

  
А стили на них вешаются так:  

```
::-webkit-input-placeholder { color:#999; }:-moz-placeholder { color:#999; }:-ms-input-placeholder { color:#999; }
```
