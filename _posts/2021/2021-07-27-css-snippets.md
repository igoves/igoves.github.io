---
title: "CSS snippets"
date: ""
categories: 
  - "css"
---

**Clearfix**

```
.clearfix:before, .container:after { content: ""; display: table; }.clearfix:after { clear: both; }/* IE 6/7 */.clearfix { zoom: 1; }
```

  
**Cross-Browser Transparency**

```
.transparent {    filter: alpha(opacity=50); /* internet explorer */    -khtml-opacity: 0.5;      /* khtml, old safari */    -moz-opacity: 0.5;       /* mozilla, netscape */    opacity: 0.5;           /* fx, safari, opera */}
```

  
**General Media Queries**

```
/* Smartphones (portrait and landscape) ----------- */@media only screen and (min-device-width : 320px) and (max-device-width : 480px) {  /* Styles */}/* Smartphones (landscape) ----------- */@media only screen and (min-width : 321px) {  /* Styles */}/* Smartphones (portrait) ----------- */@media only screen and (max-width : 320px) {  /* Styles */}/* iPads (portrait and landscape) ----------- */@media only screen and (min-device-width : 768px) and (max-device-width : 1024px) {  /* Styles */}/* iPads (landscape) ----------- */@media only screen and (min-device-width : 768px) and (max-device-width : 1024px) and (orientation : landscape) {  /* Styles */}/* iPads (portrait) ----------- */@media only screen and (min-device-width : 768px) and (max-device-width : 1024px) and (orientation : portrait) {  /* Styles */}/* Desktops and laptops ----------- */@media only screen and (min-width : 1224px) {  /* Styles */}/* Large screens ----------- */@media only screen and (min-width : 1824px) {  /* Styles */}/* iPhone 4 ----------- */@media only screen and (-webkit-min-device-pixel-ratio:1.5), only screen and (min-device-pixel-ratio:1.5) {  /* Styles */}
```

  
**Custom Text Selection**

```
::selection { background: #e2eae2; }  ::-moz-selection { background: #e2eae2; }  ::-webkit-selection { background: #e2eae2; }
```

  
**Fullscreen Backgrounds with CSS3**

```
html {       background: url('images/bg.jpg') no-repeat center center fixed;       -webkit-background-size: cover;      -moz-background-size: cover;      -o-background-size: cover;      background-size: cover;  }  
```

  
**Vertically Centered Content**

```
.container {      min-height: 6.5em;      display: table-cell;      vertical-align: middle;  }  
```

  
**@font-face Template**

```
@font-face {      font-family: 'MyWebFont';      src: url('webfont.eot'); /* IE9 Compat Modes */      src: url('webfont.eot?#iefix') format('embedded-opentype'), /* IE6-IE8 */      url('webfont.woff') format('woff'), /* Modern Browsers */      url('webfont.ttf')  format('truetype'), /* Safari, Android, iOS */      url('webfont.svg#svgFontName') format('svg'); /* Legacy iOS */  }        body {      font-family: 'MyWebFont', Arial, sans-serif;  }  
```

  
**CSS3 Zebra Stripes**

```
tbody tr:nth-child(odd) {      background-color: #ccc;  }  
```

  
**CSS3 Column Text**

```
#columns-3 {      text-align: justify;      -moz-column-count: 3;      -moz-column-gap: 12px;      -moz-column-rule: 1px solid #c4c8cc;      -webkit-column-count: 3;      -webkit-column-gap: 12px;      -webkit-column-rule: 1px solid #c4c8cc;  }  
```

  
**CSS Fixed Footer**

```
#footer {      position: fixed;      left: 0px;      bottombottom: 0px;      height: 30px;      width: 100%;      background: #444;  }     /* IE 6 */  * html #footer {      position: absolute;      top: expression((0-(footer.offsetHeight)+(document.documentElement.clientHeight ? document.documentElement.clientHeight : document.body.clientHeight)+(ignoreMe = document.documentElement.scrollTop ? document.documentElement.scrollTop : document.body.scrollTop))+'px');  }  
```

  
**Transparent PNG Fix for IE6**

```
.bg {    width:200px;    height:100px;    background: url(/folder/yourimage.png) no-repeat;    _background:none;    _filter:progid:DXImageTransform.Microsoft.AlphaImageLoader(src='/folder/yourimage.png',sizingMethod='crop');}/* 1px gif method */img, .png {    position: relative;    behavior: expression((this.runtimeStyle.behavior="none")&&(this.pngSet?this.pngSet=true:(this.nodeName == "IMG" && this.src.toLowerCase().indexOf('.png')>-1?(this.runtimeStyle.backgroundImage = "none",       this.runtimeStyle.filter = "progid:DXImageTransform.Microsoft.AlphaImageLoader(src='" + this.src + "', sizingMethod='image')",       this.src = "images/transparent.gif"):(this.origBg = this.origBg? this.origBg :this.currentStyle.backgroundImage.toString().replace('url("','').replace('")',''),       this.runtimeStyle.filter = "progid:DXImageTransform.Microsoft.AlphaImageLoader(src='" + this.origBg + "', sizingMethod='crop')",       this.runtimeStyle.backgroundImage = "none")),this.pngSet=true));}
```

  
**Cross-Browser Minimum Height**

```
#container {      min-height: 550px;      height: auto !important;      height: 550px;  }  
```

  
**Style Links Based on Filetype**

```
/* external links */a[href^="http://"] {    padding-right: 13px;    background: url('external.gif') no-repeat center right;} /* emails */a[href^="mailto:"] {    padding-right: 20px;    background: url('email.png') no-repeat center right;} /* pdfs */a[href$=".pdf"] {    padding-right: 18px;    background: url('acrobat.png') no-repeat center right;}
```

  
**Display URLS in a Printed Webpage**

```
@media print   {      a:after {        content: " [" attr(href) "] ";      }    }  
```

  
  
**Подсвечивающийся инпут**

```
input[type=text], textarea {      -webkit-transition: all 0.30s ease-in-out;      -moz-transition: all 0.30s ease-in-out;      -ms-transition: all 0.30s ease-in-out;      -o-transition: all 0.30s ease-in-out;      outline: none;      padding: 3px 0px 3px 3px;      margin: 5px 1px 3px 0px;      border: 1px solid #ddd;  }     input[type=text]:focus, textarea:focus {      box-shadow: 0 0 5px rgba(81, 203, 238, 1);      padding: 3px 0px 3px 3px;      margin: 5px 1px 3px 0px;      border: 1px solid rgba(81, 203, 238, 1);  } 
```

  
**Флажек скидки**

```
.featureBanner {      position: relative;      margin: 20px  }  .featureBanner:before {      content: "Скидка 10%";      position: absolute;      top: 5px;      left: -8px;      padding-right: 10px;      color: #232323;      font-weight: bold;      height: 0px;      border: 15px solid #ffa200;      border-right-color: transparent;      line-height: 0px;      box-shadow: -0px 5px 5px -5px #000;      z-index: 1;  }    .featureBanner:after {      content: "";      position: absolute;      top: 35px;      left: -8px;      border: 4px solid #89540c;      border-left-color: transparent;      border-bottom-color: transparent;  } 
```
