---
title: "Highway - простой быстрый js скрипт создания роутингов  без зависимостей"
categories: 
  - "js"
---

```
(function() {
    function HomeViewModel() {
    }
    HomeViewModel.prototype.init = function(element) {
        //this will be called when page is navigated to
    }
    HomeViewModel.prototype.destroy = function() {
        //this is called when page is left
    }
    highway.configureRoutes({
        routes: [{
            state: 'home',
            template: 'pages/home/home.html',
            viewmodel: new HomeViewModel()
        }, {
            state: 'gettingstarted',
            template: 'pages/gettingstarted/gettingstarted.html'
        }, {
            state: 'changelog',
            template: '#changelog'
        }],
        default: 'home'
    });
})();
```

  
[https://github.com/ashh640/Highway](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2FzaGg2NDAvSGlnaHdheQ%3D%3D)
