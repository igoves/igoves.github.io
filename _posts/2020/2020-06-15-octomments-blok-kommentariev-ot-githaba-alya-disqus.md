---
title: "Octomments - блок комментариев от гитхаба аля Disqus"
date: "2020-06-15"
categories: 
  - "note"
tags: 
  - "comments"
  - "github"
---

```
<script src="https://unpkg.com/octomments/build/ocs.min.js"></script>
<script>
  Octomments({
    github: {
      owner: 'krasimir',
      repo: 'octomments',
    },
    issueNumber: 1,
    renderer: [OctommentsRenderer, '#comments']
  }).init();
<script>
```

[https://ocs.now.sh/](https://ocs.now.sh/)
