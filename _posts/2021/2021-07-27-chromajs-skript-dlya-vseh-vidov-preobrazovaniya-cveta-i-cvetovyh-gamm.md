---
title: "chroma.js - скрипт для всех видов преобразования цвета и цветовых гамм."
categories: 
  - "js"
---

Initiate and manipulate colors:  
chroma(\\'#D4F880\\').darken().hex(); // #9BC04B  
  
Working with color scales is easy, too:  
scale = chroma.scale(\[\\'white\\', \\'red\\'\]);  
scale(0.5).hex(); // #FF7F7F  
  
Lab/Lch interpolation looks better than than RGB  
chroma.scale(\[\\'white\\', \\'red\\'\]).mode(\\'lab\\');  
  
Custom domains! Quantiles! Color Brewer!!  
chroma.scale(\\'RdYlBu\\').domain(myValues, 7, \\'quantiles\\');  
  
And why not use logarithmic color scales once in your life?  
chroma.scale(\[\\'lightyellow\\', \\'navy\\'\]).domain(\[1, 100000\], 7, \\'log\\');

  
[https://github.com/gka/chroma.js](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2drYS9jaHJvbWEuanM%3D)
