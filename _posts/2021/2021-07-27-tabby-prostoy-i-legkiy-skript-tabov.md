---
title: "Tabby - простой и легкий скрипт табов"
categories: 
  - "js"
---

Для кнопок

```
<div class="tabs">
    <button class="active" data-tab="#tab1">Superheroes</button>
    <button data-tab="#tab2">Ice Cream</button>
    <button data-tab="#tab3">Seasons</button>
</div>

<div class="tabs-content">
    <div class="tabs-pane active" id="tab1">
        Superheros
        ...
    </div>

    <div class="tabs-pane" id="tab2">
        Ice Cream
        ...
    </div>

    <div class="tabs-pane" id="tab3">
        Seasons
        ...
    </div>
</div>
```

  
Для списков

```
<ul class="tabs">
    <li class="active"><a class="active" data-tab="#tab1" href="#">Superheroes</a></li>
    <li><a data-tab="#tab2" href="#">Ice Cream</a></li>
    <li><a data-tab="#tab3" href="#">Seasons</a></li>
</ul>

<div class="tabs-content">
    <div class="tabs-pane active" id="tab1">
        Superheros
        ...
    </div>
    ...
</div>
```

  
Инициализация

```
<script>
    tabby.init();
</script>
```

  
Настройки

```
tabby.init({
    selector: '[data-tab]', // Tab toggle selector
    toggleActiveClass: 'active', // Class added to active toggle elements
    contentActiveClass: 'active', // Class added to active tab content areas
    initClass: 'js-tabby', // Class added to <html> element when initiated
    callback: function ( toggle, tabID ) {} // Function that's run after tab content is toggled
});
```

  
[https://github.com/cferdinandi/tabby/](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2NmZXJkaW5hbmRpL3RhYmJ5Lw%3D%3D)
