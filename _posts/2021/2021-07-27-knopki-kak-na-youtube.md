---
title: "Кнопки как на youtube"
date: ""
categories: 
  - "css"
tags: 
  - "buttons"
  - "youtube"
  - "knopki"
---

![Кнопки как на youtube](images/1330720682_hoverstate.png "Кнопки как на youtube")

  
[ДЕМО](https://dev.xfor.top/go/aHR0cDovL2Nzcy10cmlja3MuY29tL2V4YW1wbGVzL1lvdVR1YmVCdXR0b25zLw%3D%3D)  
  
HTML  

```
<button class="button" role="button">   Button #1</button>
```

  
  
CSS  

```
.button {   border: 1px solid #DDD;   border-radius: 3px;   text-shadow: 0 1px 1px white;   -webkit-box-shadow: 0 1px 1px #fff;   -moz-box-shadow:    0 1px 1px #fff;   box-shadow:         0 1px 1px #fff;   font: bold 11px Sans-Serif;   padding: 6px 10px;   white-space: nowrap;   vertical-align: middle;   color: #666;   background: transparent;   cursor: pointer;}.button:hover, .button:focus {   border-color: #999;   background: -webkit-linear-gradient(top, white, #E0E0E0);   background:    -moz-linear-gradient(top, white, #E0E0E0);   background:     -ms-linear-gradient(top, white, #E0E0E0);   background:      -o-linear-gradient(top, white, #E0E0E0);   -webkit-box-shadow: 0 1px 2px rgba(0,0,0,0.25), inset 0 0 3px #fff;   -moz-box-shadow:    0 1px 2px rgba(0,0,0,0.25), inset 0 0 3px #fff;   box-shadow:         0 1px 2px rgba(0,0,0,0.25), inset 0 0 3px #fff;}.button:active {   border: 1px solid #AAA;   border-bottom-color: #CCC;   border-top-color: #999;   -webkit-box-shadow: inset 0 1px 2px #aaa;   -moz-box-shadow:    inset 0 1px 2px #aaa;   box-shadow:         inset 0 1px 2px #aaa;   background: -webkit-linear-gradient(top, #E6E6E6, gainsboro);   background:    -moz-linear-gradient(top, #E6E6E6, gainsboro);   background:     -ms-linear-gradient(top, #E6E6E6, gainsboro);   background:      -o-linear-gradient(top, #E6E6E6, gainsboro);}
```
