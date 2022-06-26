---
title: "mathjax - js генерация формул svg"
date: "2020-11-02"
categories: 
  - "js"
tags: 
  - "svg"
  - "formuly"
---

```
require('mathjax').init({
  loader: {load: ['input/tex', 'output/svg']}
}).then((MathJax) => {
  const svg = MathJax.tex2svg('\\frac{1}{x^2-1}', {display: true});
  console.log(MathJax.startup.adaptor.outerHTML(svg));
}).catch((err) => console.log(err.message));
```

[https://www.mathjax.org/](https://www.mathjax.org/)
