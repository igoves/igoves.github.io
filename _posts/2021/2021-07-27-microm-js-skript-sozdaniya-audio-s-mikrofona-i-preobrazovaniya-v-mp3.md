---
title: "microm - js скрипт создания аудио с микрофона и преобразования в mp3"
date: ""
categories: 
  - "js"
---

Пример использования  

```
function start() {
  microm.startRecording().then(function() {
    console.log('recording...')
  }).catch(function() {
    console.log('error recording');
  });
}

function stop() {
  microm.stop().then(function(result) {
    mp3 = result;
    console.log(mp3.url, mp3.blob, mp3.buffer);

    play();
    download();
  });
}
```

  
[https://github.com/zzarcon/microm](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3p6YXJjb24vbWljcm9t) | [Демка](https://dev.xfor.top/go/aHR0cDovL3p6YXJjb24uZ2l0aHViLmlvL21pY3JvbS8%3D)
