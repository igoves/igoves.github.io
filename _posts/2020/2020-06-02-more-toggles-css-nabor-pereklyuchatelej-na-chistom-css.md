---
title: "More Toggles.css - набор переключателей на чистом   css"
date: "2020-06-02"
categories: 
  - "css"
tags: 
  - "checkbox"
  - "toggles"
---

```
<div class="mt-ios"> 
  <input id="5" type="checkbox" />
  <label for="5"></label>
</div>

<script>
  const toggle = document.getElementById('5');

  toggle.addEventListener('change', (event) => {
    if (event.target.checked) {
      alert('checked');
    } else {
      alert('not checked');
    }
  });
</script>
```

- Чистый CSS
- 13 различных стилей
- идеальное масштабирование

[https://github.com/JNKKKK/MoreToggles.css](https://github.com/JNKKKK/MoreToggles.css)
