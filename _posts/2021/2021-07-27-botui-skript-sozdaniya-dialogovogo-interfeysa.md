---
title: "botui - скрипт создания диалогового интерфейса"
categories: 
  - "js"
---

![botui - скрипт создания диалогового интерфейса](images/preview.png "botui - скрипт создания диалогового интерфейса")

  
Пример

```
var botui = new BotUI('botui-app'); // give it the id of container

botui.message.bot({ // show first message
  delay: 200,
  content: 'hello'
}).then(function () {
  return botui.message.bot({ // second one
    delay: 1000, // wait 1 sec.
    content: 'how are you?'
  });
}).then(function () {
  return botui.action.button({ // let user do something
    delay: 1000,
    action: [
      {
        text: 'Good',
        value: 'good'
      },
      {
        text: 'Really Good',
        value: 'really_good'
      }
    ]
  });
}).then(function (res) {
  return botui.message.bot({
    delay: 1000,
    content: 'You are feeling ' + res.text + '!'
  });
});
```

  
[https://github.com/moinism/botui](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL21vaW5pc20vYm90dWk%3D)
