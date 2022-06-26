---
title: "Еще один ява-скрипт заменяющий стандартные checkbox и radio buttons"
date: ""
categories: 
  - "js"
tags: 
  - "checkbox"
  - "radio-buttons"
---

![Еще один ява-скрипт заменяющий стандартные checkbox и radio buttons](images/1311106516_radio.jpg "Еще один ява-скрипт заменяющий стандартные checkbox и radio buttons")

  
HTML  

```
<label class="label_check" for="sample-check"> <input name="sample-check" id="sample-check" value="1" type="checkbox" /> Sample Label </label><label class="label_radio" for="sample-radio"> <input name="sample-radio" id="sample-radio" value="1" type="radio" /> Sample Label </label>
```

  
CSS  

```
.has-js .label_check,.has-js .label_radio { padding-left: 34px; }.has-js .label_radio { background: url(radio-off.png) no-repeat; }.has-js .label_check { background: url(check-off.png) no-repeat; }.has-js label.c_on { background: url(check-on.png) no-repeat; }.has-js label.r_on { background: url(radio-on.png) no-repeat; }.has-js .label_check input,.has-js .label_radio input { position: absolute; left: -9999px; }
```

  
JS  

```
var d = document;var safari = (navigator.userAgent.toLowerCase().indexOf('safari') != -1) ? true : false;var gebtn = function(parEl,child) { return parEl.getElementsByTagName(child); };onload = function() { var body = gebtn(d,'body')[0]; body.className = body.className && body.className != '' ? body.className + ' has-js' : 'has-js'; if (!d.getElementById || !d.createTextNode) return; var ls = gebtn(d,'label'); for (var i = 0; i < ls.length; i++) { var l = ls[i]; if (l.className.indexOf('label_') == -1) continue; var inp = gebtn(l,'input')[0]; if (l.className == 'label_check') { l.className = (safari && inp.checked == true || inp.checked) ? 'label_check c_on' : 'label_check c_off'; l.onclick = check_it; }; if (l.className == 'label_radio') { l.className = (safari && inp.checked == true || inp.checked) ? 'label_radio r_on' : 'label_radio r_off'; l.onclick = turn_radio; }; };};var check_it = function() { var inp = gebtn(this,'input')[0]; if (this.className == 'label_check c_off' || (!safari && inp.checked)) { this.className = 'label_check c_on'; if (safari) inp.click(); } else { this.className = 'label_check c_off'; if (safari) inp.click(); };};var turn_radio = function() { var inp = gebtn(this,'input')[0]; if (this.className == 'label_radio r_off' || inp.checked) { var ls = gebtn(this.parentNode,'label'); for (var i = 0; i < ls.length; i++) { var l = ls[i]; if (l.className.indexOf('label_radio') == -1) continue; l.className = 'label_radio r_off'; }; this.className = 'label_radio r_on'; if (safari) inp.click(); } else { this.className = 'label_radio r_off'; if (safari) inp.click(); };};
```

  
[ДЕМО](https://dev.xfor.top/go/aHR0cDovL2F6ZXJvLm9yZy9yYWRpby9pbmRleC5odG1s)
