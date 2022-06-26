---
title: "PHP Browser - библиотека определения браузера клиента средствами PHP"
date: ""
categories: 
  - "php"
---

**Браузеры которые определяет**  
Opera, Opera Mini, WebTV, Internet Explorer, Pocket Internet Explorer, Konqueror, iCab, OmniWeb, Firebird, Firefox, Iceweasel, Shiretoko, Mozilla, Amaya, Lynx, Safari, Chrome, Navigator, GoogleBot, Yahoo! Slurp, W3C Validator, BlackBerry, IceCat, Nokia S60 OSS Browser, Nokia Browser, MSN Browser, MSN Bot, Netscape Navigator, Galeon, NetPositive, Phoenix, SeaMonkey  
  
**Пример использования**

```
use Browser\\Browser;

$browser = new Browser;
if ($browser->getName() === $browser::IE && $browser->getVersion() < 8) {
    echo 'Please upgrade your browser.';
}
```

  
**Операционные системы которые определяет**  
Windows, OS X, iOS, Android, Linux, SymbOS, Nokia, BlackBerry, FreeBSD, OpenBSD, NetBSD, OpenSolaris, SunOS, OS2, BeOS  
  
**Пример исползования**

```
use Browser\\Os;

$os = new Os;
if ($os->getName() == $os::IOS) {
    echo 'You are using an iOS device.';
}
```

  
**Пример определения языка**

```
use Browser\\Language;

$language = new Language;
if ($language->getLanguage() == 'de') {
    echo 'Get this website in german.';
}
```
