---
title: "bstreeview - плагин для создания дерева категорий на twitter bootstrap 4"
date: "2020-06-04"
categories: 
  - "js"
tags: 
  - "tb4"
  - "treeview"
---

![](https://github.com/chniter/bstreeview/raw/master/screeshots/bstreeview.PNG?raw=true)

```
function getTree() {
  // Some logic to retrieve, or generate tree structure
  return data;
}

$('#tree').bstreeview({ data: getTree() });

var tree = [
  {
    text: "Node 1",
    icon: "fa fa-folder",
    nodes: [
      {
        text: "Sub Node 1",
        icon: "fa fa-folder",
        nodes: [
          {
            id:    "sub-node-1",
            text:  "Sub Child Node 1",
            icon:  "fa fa-folder",
            class: "nav-level-3",
            href:  "https://google.com"
          },
          {
            text: "Sub Child Node 2",
            icon: "fa fa-folder"
          }
        ]
      },
      {
        text: "Sub Node 2",
         icon: "fa fa-folder"
      }
    ]
  },
  {
    text: "Node 2",
    icon: "fa fa-folder"
  }
];
```

[https://github.com/chniter/bstreeview](https://github.com/chniter/bstreeview)
