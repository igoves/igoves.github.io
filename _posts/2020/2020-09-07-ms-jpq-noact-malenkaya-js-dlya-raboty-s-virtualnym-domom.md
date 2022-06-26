---
title: "ms-jpq/noact - маленькая JS для работы с виртуальным домом"
date: "2020-09-07"
categories: 
  - "js"
tags: 
  - "dom"
  - "js"
  - "virtual"
---

import { button, div } from "./NoactElements"
const component1 = div({},
    button({ onclick: () => alert(":D"), txt: "+" }),
    div({ txt: "♥" }),
    button({ onclick: () => alert("D:"), txt: "-" })
)

`На выходе получаем:`

<div>
  <button>+</button>
  <div>♥</div>
  <button>-</button>
</div>

[https://github.com/ms-jpq/noact](https://github.com/ms-jpq/noact)
