---
title: "abDetector - детектор адблока на чистом js"
categories: 
  - "js"
---

```
window.onload = function() {
	var iframe = document.createElement('iframe'),
		randomNum = Math.floor(Math.random() * (10000 - 123 + 1)) + 123,
		protocol = window.location.protocol;

	iframe.src = protocol +"//google.com/"+ randomNum +"/ads.html";
	iframe.height = ".1px";
	iframe.width = ".1px";
	iframe.id = 'some-ad';

	getRequest(iframe, function (response) { // On Success
		document.body.appendChild(iframe);
	}, function (xhr, status) { // On error
		if (status === 0) // Request aborted
	  		document.body.appendChild(iframe);
	});

	setTimeout(function() {
		var someAd = document.getElementById('some-ad');
		if(someAd === null ||
		someAd.style.display == "none" ||
		someAd.style.display == "hidden" ||
		someAd.style.visibility == "hidden" ||
		someAd.offsetHeight === 0)
			document.getElementById('ab-message').style.display = 'block';
		else
			someAd.remove();
	}, 500);
};

function getRequest (iframe, success, error) {
	var xhr = XMLHttpRequest ? new XMLHttpRequest() : new ActiveXObject("Microsoft.XMLHTTP");
	xhr.open("GET", iframe.src);
	xhr.onreadystatechange = function(){
		if (xhr.readyState == 4)
			if (xhr.status == 200) // Loaded successfully
				success(xhr.responseText);
			else // For any other error
				error(xhr, xhr.status);
	};
	xhr.send();
}
```

  
[https://github.com/R4meau/abDetector](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL1I0bWVhdS9hYkRldGVjdG9y)
