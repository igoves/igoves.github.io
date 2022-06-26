---
title: "Чтение изображеня на стороне клиента HTML5 и JS"
categories: 
  - "js"
---

```
<style>  .thumb {    height: 75px;    border: 1px solid #000;    margin: 10px 5px 0 0;  }</style><input type="file" id="files" name="files[]" multiple /><output id="list"></output><script>  function handleFileSelect(evt) {    var files = evt.target.files; // FileList object    // Loop through the FileList and render image files as thumbnails.    for (var i = 0, f; f = files[i]; i++) {      // Only process image files.      if (!f.type.match('image.*')) {        continue;      }      var reader = new FileReader();      // Closure to capture the file information.      reader.onload = (function(theFile) {        return function(e) {          // Render thumbnail.          var span = document.createElement('span');          span.innerHTML = ['<img class="thumb" src="', e.target.result,                            '" title="', escape(theFile.name), '"/>'].join('');          document.getElementById('list').insertBefore(span, null);        };      })(f);      // Read in the image file as a data URL.      reader.readAsDataURL(f);    }  }  document.getElementById('files').addEventListener('change', handleFileSelect, false);</script>
```

  
Здесь вызывается функция reader.readAsDataURL() и выводится уменьшенное изображение путем установки для атрибута src значения, представляющего URL данных  
Результат будет:  

![Чтение изображеня на стороне клиента HTML5 и JS](images/1409838251_untitled-8.png "Чтение изображеня на стороне клиента HTML5 и JS")
