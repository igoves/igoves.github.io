---
title: "Как создать автозаполнение ввода на чистом HTML"
date: "2020-07-02"
categories: 
  - "xhtml"
tags: 
  - "autocomplite"
  - "select"
---

```
<label for="wizards">Who's the best wizard?</label>
<input type="text" id="wizards" name="wizards" list="wizards-list">

<datalist id="wizards-list">
	<option>Harry Potter</option>
	<option>Hermione</option>
	<option>Dumbledore</option>
	<option>Merlin</option>
	<option>Gandalf</option>
</datalist>
```

Элемент datalist работает во всех современных браузерах, вплоть до IE10.
