---
title: "xkeshi/image-compressor - js компрессор изображений"
categories: 
  - "js"
---

```
<input type="file" id="file" accept="image/*">
import axios from 'axios';
import ImageCompressor from 'image-compressor';

document.getElementById('file').addEventListener('change', (e) => {
  const file = e.target.files[0];

  if (!file) {
    return;
  }

  new ImageCompressor(file, {
    quality: .6,
    success(result) {
      const formData = new FormData();

      formData.append('file', result);

      // Send the compressed image file to server with XMLHttpRequest.
      axios.post('/path/to/upload', formData).then(() => {
        console.log('Upload success!');
      });
    },
    error(e) {
      console.log(e.message);
    },
  });
})
```

  
Работает на последних версиях браузеров  
[https://github.com/xkeshi/image-compressor](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3hrZXNoaS9pbWFnZS1jb21wcmVzc29y)
