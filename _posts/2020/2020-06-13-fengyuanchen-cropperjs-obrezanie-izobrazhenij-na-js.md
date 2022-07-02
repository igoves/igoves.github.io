---
title: "fengyuanchen / cropperjs - обрезание изображений на js"
date: "2020-06-13"
categories: 
  - "js"
tags: 
  - "crop"
  - "image"
---

```
import axios from 'axios';
import Compressor from 'compressorjs';

document.getElementById('file').addEventListener('change', (e) => {
  const file = e.target.files[0];

  if (!file) {
    return;
  }

  new Compressor(file, {
    quality: 0.6,
    success(result) {
      const formData = new FormData();

      // The third parameter is required for server
      formData.append('file', result, result.name);

      // Send the compressed image file to server with XMLHttpRequest.
      axios.post('/path/to/upload', formData).then(() => {
        console.log('Upload success');
      });
    },
    error(err) {
      console.log(err.message);
    },
  });
});
```

[https://github.com/fengyuanchen/cropperjs](https://github.com/fengyuanchen/cropperjs)
