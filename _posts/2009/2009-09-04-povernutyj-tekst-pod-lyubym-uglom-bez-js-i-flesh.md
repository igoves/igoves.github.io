---
title: "Повернутый текст под любым углом без JS и флеш"
date: "2009-09-04"
categories: 
  - "note"
tags: 
  - "gradus"
  - "povorot"
  - "teks"
  - "hak"
---

Приступим. Для начала нам нужен блок: css:

```
.vertical { overflow:hidden; line-height:30px; position:relative; white-space:nowrap; width:30px; height:200px; border:1px solid #999; }
```

html:

```
<div class="vertical"></div>
```

Для современных браузеров будем использовать svg:

css:

```
.vertical object { width:30px; height:200px; display:block; } - задаем ширину равную высоте и высоту равную ширине обрамляющего блока.
```

html:

```
<object type="image/svg+xml" data="data:image/svg+xml; charset=utf-8,<svg xmlns="http://www.w3.org/2000/svg"><text x="-200" y="18" fill="#000000" transform="rotate(-90)">вертикальный текст</text></svg>">
</object>
```

— x=\\'-200\\' - координата начала строки текста от верхней стороны object, y=\\'18\\' - координата базовой линии строки текста от левой стороны object, font-family=\\'Arial\\' font-size=\\'12\\' - размер, гарнитура шрифта, fill=\\'#000000\\' - цвет текста, transform=\\'rotate(-90)\\' - поворачиваем текст на -90 градусов. мы можем повернуть текст на любой угол Для IE всех версий:

Так как IE даже 8-й версии не поддерживает svg(разработчики сказали что у них и так было много работы), будем использовать специфические свойства: writing-mode:tb-rl; — текст размещаем вертикально сверху вниз и справа налево filter:flipv() fliph(); — отражаем по горизонтали и вертикали. css:

```
.vertical object { display:none; } - скрываем svg.
.vertical span { filter:flipv() fliph(); writing-mode:tb-rl; display:block; position:absolute; left:0; bottom:0; height:200px; width:30px; }
```

html:

```
<span>вертикальный текст</span>
```

Для текста под углом css выглядит так:

```
.vertical3 span { top:-8px; left:-31px; width:200px; writing-mode:lr-tb; filter:progid:DXImageTransform.Microsoft.Matrix(M11='0.985', M12='-0.174', M21='0.174', M22='0.985', SizingMethod=«auto expand»); }
```

top, left — эмпирические значения. находятся экспериментально. M11 = cos(угла в градусах) M12 = -sin(угла в градусах) M21 = sin(угла в градусах) M22 = cos(угла в градусах) Отрицательные значения не берем! если нам надо повернуть на -45 градусов то значения тригонометрических функций берем от угла 315 градусов.

Ограничения: Возможно сделать текст только в одну строку, и в блоке с жестко заданными размерами в пикселях.
