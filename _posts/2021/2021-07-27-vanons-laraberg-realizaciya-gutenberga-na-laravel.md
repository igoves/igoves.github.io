---
title: "VanOns/laraberg - реализация гутенберга на ларавел"
date: ""
categories: 
  - "php"
---

```
$content // This is the raw content from the Gutenberg editor
$model = new MyModel;

// Add or update the content & (if true is provided) call save() on the content object
$model->setContent($content, true);

// Get the rendered HTML inside of a container
// This is the function you should use for rendering the content on a page
$model->renderContent();

// Get the rendered content
$model->getRenderedContent();

// Get the raw content
$model->getRawContent();
```

  
[https://github.com/VanOns/laraberg](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL1Zhbk9ucy9sYXJhYmVyZw%3D%3D)
