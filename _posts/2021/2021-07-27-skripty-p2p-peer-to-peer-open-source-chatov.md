---
title: "Скрипты P2P (peer to peer) open-source чатов"
date: ""
categories: 
  - "note"
---

**PeerJS** - скрипт основан на WebRTC, и работает на PeerServer который работает на node.js  
Коннект

```
var conn = peer.connect('another-peers-id');
conn.on('open', function(){
  conn.send('hi!');
});
```

Получить

```
peer.on('connection', function(conn) {
  conn.on('data', function(data){
    // Will print 'hi!'
    console.log(data);
  });
});
```

[https://github.com/peers/peerjs](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3BlZXJzL3BlZXJqcw%3D%3D)  
  
**otr.to** - скрипт зашифрованного чата с само уничтожающимися сообщениями  

[![Скрипты P2P (peer to peer) open-source чатов ](images/devices.png "Скрипты P2P (peer to peer) open-source чатов ")](https://sdelements.github.io/lets-chat/assets/img/devices.png)

  
[https://github.com/sdelements/lets-chat](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3NkZWxlbWVudHMvbGV0cy1jaGF0)
