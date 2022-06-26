---
title: "Использование картинок в html письмах"
date: ""
categories: 
  - "note"
---

**Какой формат выбрать?**  
jpeg - используйте для сложных изображений без прозрачности  
png - картинки с прозрачностью  
gif - для логотипов, иконок и когда вам нужна анимация.  
  
**Как добавлять?**  
Простой способ использовать абсолютный путь

```
<img src="http://site.com/path/to/image.jpg" alt="название" width="600" border="0" style="display: block;" />
```

Недостаток. При открытии письма картинки загружаются с вашего ресурса. Иногда почтовые ящики блочат такие картинки.  
  
Другой способ это внедрять в тег [img data:uri](https://dev.xfor.top/go/aHR0cHM6Ly9ydS53aWtpcGVkaWEub3JnL3dpa2kvZCZhbXA7IzA5Nzt0YTpfVVJM)  
Недостаток, если картинки объемные письмо может стать очень тяжелым.  
  
Еще способ использовать к примеру [PHPMailer](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL1N5bmNocm8vUEhQTWFpbGVy)  
Он создает аттачи и и уже по внутреннему идентификатору из атача берет картинки

```
$mail->AddEmbeddedImage(filename, attach, name);
<img src="cid:attach" />
```
