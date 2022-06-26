---
title: "Js скрипт фильтра по тексту для страницы FAQ"
date: ""
categories: 
  - "js"
---

![Js скрипт фильтра по тексту для страницы FAQ](images/1449910801_untitled-2.png "Js скрипт фильтра по тексту для страницы FAQ")

  

```
$(function () {
     function FullTextContains(innerText, searchTerm) {
         for (x = 0; x < searchTerm.length; x++) {
             if (innerText.toLowerCase().indexOf(searchTerm[x].toLowerCase()) >= 0) {
                 return true;
             }
         }
         return false;
     }

     $('.faq').on('keyup input', function (e) {
         var text = $.trim($(this).val());
         if (e.keyCode == 13) {
             SearchFAQ(text);
         } else if (text == '') {
             SearchFAQ('');
         }
     });

     $('#btnFaqSearch').on('click', function (e) {
         var text = $.trim($('.faq').val());
         SearchFAQ(text);
     });

     function SearchFAQ(searchTermText) {
         var searchTerm = searchTermText.split(' ');
         if (searchTermText != '') {
             $(".faq-list .panel").filter(function (index) {
                 var panelText = $.trim($(this).text());
                 if (FullTextContains(panelText, searchTerm) == true) {
                     //console.log("found it");
                     return true;
                 } else {
                     //console.log("not found");
                     $(this).slideUp();
                     return false;
                 }
             }).slideDown();
         } else {
             $(".faq-list .panel").slideDown();
         }
     }
 });
```

  
Демонстрация: [http://jsfiddle.net/lesson8/u66Qa/show/](https://dev.xfor.top/go/aHR0cDovL2pzZmlkZGxlLm5ldC9sZXNzb244L3U2NlFhL3Nob3cv)
