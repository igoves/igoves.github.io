---
title: "pushjs.org - the world's most versatile desktop notifications framework reaches"
date: "2021-05-11"
categories: 
  - "js"
tags: 
  - "notification"
  - "push"
---

![](images/logo.png)

Push is the fastest way to get up and running with Javascript desktop notifications. A fairly new addition to the official specification, the Notification API allows modern browsers such as Chrome, Safari, Firefox, and IE 9+ to push notifications to a user's desktop. Push acts as a cross-browser solution to this API, falling back to use older implementations if the user's browser does not support the new API.

```
Push.create("Hello world!", {
    body: "How's it hangin'?",
    icon: '/icon.png',
    timeout: 4000,
    onClick: function () {
        window.focus();
        this.close();
    }
});
```

[https://pushjs.org/](https://pushjs.org/)
