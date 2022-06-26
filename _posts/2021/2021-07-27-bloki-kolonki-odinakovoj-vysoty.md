---
title: "Блоки-колонки одинаковой высоты"
categories: 
  - "css"
---

Может и писал, а может и нет, не помню, но сталкиваются веб-дизигнеры с этим часто.  
  
**Использование свойства display: table** [Метод 1](https://dev.xfor.top/go/aHR0cDovL3d3dy5idWlsZGludGVybmV0LmNvbS9saXZlL2VxdWFsY29sdW1ucy9tZXRob2QxLmh0bWw%3D)  
Это наиболее простой и легкий способ создания колонок одинаковой высоты, в отличие от других методов. Этот метод не работает в браузерах IE7 и ниже. (опять ИЕ выебнулся)  
  
**Использование javascript** [Метод 2](https://dev.xfor.top/go/aHR0cDovL3d3dy5idWlsZGludGVybmV0LmNvbS9saXZlL2VxdWFsY29sdW1ucy9tZXRob2QzLmh0bWw%3D)  
Главное преимущество метода – он работает во всех браузерах и вам не нужно напрягаться с CSS кодом для выравнивания высоты.  
  
**Искусственные колонки** [Метод 3](https://dev.xfor.top/go/aHR0cDovL3d3dy5idWlsZGludGVybmV0LmNvbS9saXZlL2VxdWFsY29sdW1ucy9tZXRob2QyLmh0bWw%3D)  
Очень простая реализация. Этот метод можно использовать только для макетов/колонок фиксированной ширины.  
  
**Использование раздельных блоков с фоном** [Метод 4](https://dev.xfor.top/go/aHR0cDovL3d3dy5idWlsZGludGVybmV0LmNvbS9saXZlL2VxdWFsY29sdW1ucy9tZXRob2Q0Lmh0bWw%3D) [Метод 4.1](https://dev.xfor.top/go/aHR0cDovL3d3dy5idWlsZGludGVybmV0LmNvbS9saXZlL2VxdWFsY29sdW1ucy9tZXRob2Q0LTIuaHRtbA%3D%3D)  
Этот способ основан на использовании раздельных блоков div, каждый из которых имеет свой фон и принимает значение высоты элемента, который он включает. Этот способ в деталях описан [здесь](https://dev.xfor.top/go/aHR0cDovL21hdHRoZXdqYW1lc3RheWxvci5jb20vYmxvZy9lcXVhbC1oZWlnaHQtY29sdW1ucy1jcm9zcy1icm93c2VyLWNzcy1uby1oYWNrcw%3D%3D)
