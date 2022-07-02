---
title: "cheetah-grid - the fastest open-source data table for web"
date: "2021-04-09"
categories: 
  - "js"
tags: 
  - "data"
  - "table"
---

![](images/capture.png)

```
<div id="sample" style="height: 300px; border: solid 1px #ddd;">
</div>
<script>
  // initialize
  const grid = new cheetahGrid.ListGrid({
    // Parent element on which to place the grid
    parentElement: document.querySelector('#sample'),
    // Header definition
    header: [
      {field: 'check', caption: '', width: 50, columnType: 'check', action: 'check'},
      {field: 'personid', caption: 'ID', width: 100},
      {field: 'fname', caption: 'First Name', width: 200},
      {field: 'lname', caption: 'Last Name', width: 200},
      {field: 'email', caption: 'Email', width: 250},
    ],
    // Array data to be displayed on the grid
    records,
    // Column fixed position
    frozenColCount: 2,
  });
</script>
```

[https://github.com/future-architect/cheetah-grid](https://github.com/future-architect/cheetah-grid)
