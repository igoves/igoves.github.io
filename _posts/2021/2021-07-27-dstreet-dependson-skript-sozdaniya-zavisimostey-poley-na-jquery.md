---
title: "dstreet/dependsOn - скрипт создания зависимостей полей на jQuery"
categories: 
  - "js"
---

```
<form id="myForm">
	<label for="myCheck">Check Me</label>
	<input type="checkbox" id="myCheck">

	<label for="myText">Input</label>
	<input type="text" id="myText" value="">
</form>
```

  

```
$('#myText').dependsOn({
	// The selector for the depenency
	'#myCheck': {
		// The dependency qualifiers
		enabled: true,
		checked: true
	}
});
```

  
[https://github.com/dstreet/dependsOn](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2RzdHJlZXQvZGVwZW5kc09u) | [ДЕМО](https://dev.xfor.top/go/aHR0cDovL2RzdHJlZXQuZ2l0aHViLmlvL2RlcGVuZHNPbi8jZXhhbXBsZXM%3D)
