---
title: "cкрыть раздел диска в windows"
date: ""
categories: 
  - "note"
tags: 
  - "bezopasnost"
  - "informaciya"
  - "konfidencialnost"
---

Чтобы скрыть-показать разделы диска в windows нужно использовать два .bat файла:  
  
**hide\_D.bat**:  

```
diskpart /s hideg.scn
```

  
**show\_D.bat**:  

```
diskpart /s showg.scn
```

  

```
hideg.scn:select volume 4remove letter=dEXIT
```

  

```
showg.scn:select volume 4assign letter=dEXIT
```

  
Чтобы узнать номер раздела, запустите diskpart и там: **LIST VOLUME**  
  
пс: truecrypt + эта фича избавит Вас от геммороя с конфиденциальными данными.
