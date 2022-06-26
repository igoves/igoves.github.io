---
title: "Recordy - скрипт записи аудио с браузера"
date: ""
categories: 
  - "js"
---

Пример

```
const audioCtx = new AudioContext();
const r = new Recordy(audioCtx);

r.getInput()
  .then(val => {
    r.startRecording();

    window.setTimeout(() => {
      r.stopRecording(true)
        .then(audio => {
          audio.play();
        });
    }, 1000);
    r.toSpeaker(0.4);
    r.effects.bitcrusher.enable();
  });
```

  
[https://github.com/scriptify/Recordy](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3NjcmlwdGlmeS9SZWNvcmR5)
