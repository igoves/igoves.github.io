---
title: "Поиск на Ajax"
categories: 
  - "php"
tags: 
  - "php"
  - "ayaks"
  - "poisk"
---

![Поиск на Ajax](images/1298128890_autosuggest.png "Поиск на Ajax")

  
HTML  

```
<form id="searchForm" name="searchForm" method="post" action="javascript:insertTask();"><div class="searchInput"><input name="searchq" type="text" id="searchq" size="30" onkeyup="javascript:searchNameq()"/><input type="button" name="submitSearch" id="submitSearch" value="Search" onclick="javascript:searchNameq()"/></div></form><h3>Search Results</h3><div id="msg">Type something into the input field</div><div id="search-result"></div>
```

  
JS  

```
function createObject() {var request_type;var browser = navigator.appName;if(browser == "Microsoft Internet Explorer"){request_type = new ActiveXObject("Microsoft.XMLHTTP");} else {request_type = new XMLHttpRequest();}return request_type;}var http = createObject();function searchNameq() {searchq = encodeURI(document.getElementById('searchq').value);document.getElementById('msg').style.display = "block";document.getElementById('msg').innerHTML = "Searching for <strong>" + searchq+"";// Set te random number to add to URL requestnocache = Math.random();http.open('get', 'in-search.php?name='+searchq+'&nocache = '+nocache);http.onreadystatechange =  searchNameqReply;http.send(null);}function searchNameqReply() {if(http.readyState == 4){var response = http.responseText;document.getElementById('search-result').innerHTML = response;}}
```

  
php in-search.php  

```
<?phpinclude('config.php');$searchq = $_GET['name'];$getName = mysql_query('SELECT * FROM USER WHERE name LIKE "%'.addslashes($searchq).'%"');while ($row = mysql_fetch_array($getName))    echo $row['name'] . '<br/>';?>
```
