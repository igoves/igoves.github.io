---
title: "power-mode-input - js script can make your text input box more compelling"
date: ""
categories: 
  - "js"
---

![power-mode-input - js script can make your text input box more compelling](images/01.gif "power-mode-input - js script can make your text input box more compelling")

  

```
import PowerModeInput from "power-mode-input";

const input = document.getElementById("obinput");
PowerModeInput.make(input);

// close PowerModeInput
PowerModeInput.close(input);

// destroy PowerModeInput
PowerModeInput.destroy();

// another usage
PowerModeInput.make(".phone", {
  height: 5,
  tha: [0, 360],
  g: 0.5,
  num: 5,
  radius: 6,
  circle: true,
  alpha: [0.75, 0.1],
  color: "random"
});
```

  
[https://github.com/lindelof/power-mode-input](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2xpbmRlbG9mL3Bvd2VyLW1vZGUtaW5wdXQ%3D)
