---
title: "gDriveSync.js - обертка на js для работы с Google Drive API v3"
date: ""
categories: 
  - "js"
---

Подключаем  

```
script src="../lib/login.service.js"></script>
<script src="../lib/drive.service.js"></script>
```

  
Инициализируем  

```
var SCOPES = 'https://www.googleapis.com/auth/drive.file'
      var CLIENT_ID = 'YOUR CLIENT ID';
      DISCOVERY_DOCS = ['https://www.googleapis.com/discovery/v1/apis/drive/v3/rest'];
      window.loginService = new LoginService(CLIENT_ID, SCOPES, DISCOVERY_DOCS);
```

  
И используем методы initClient, signIn, signOut, userProfile, saveFile, loadFile, listFiles  
[https://github.com/vitogit/gDriveSync.js](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3ZpdG9naXQvZ0RyaXZlU3luYy5qcw%3D%3D)
