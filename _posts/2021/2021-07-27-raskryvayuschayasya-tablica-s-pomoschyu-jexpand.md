---
title: "Раскрывающаяся таблица с помощью jExpand"
date: ""
categories: 
  - "js"
---

![Раскрывающаяся таблица с помощью jExpand](images/1404310020_result.png "Раскрывающаяся таблица с помощью jExpand")

  
**HTML**  

```
<table id="example_table">    <tr>        <th>Column header 1</th>        <th>Column header 2</th>        <th>Column header 3</th>        <th>Column header 4</th>        <th>Column header 5</th>    </tr>    <tr>        <td>Record 1</td>        <td>value 1</td>        <td>value 2</td>        <td>value 3</td>        <td>value 4</td>    </tr>    <tr>        <td colspan="5">            <!-- additional custom info is here (for Record 1) -->          </td>    </tr>    <tr>        <td>Record 2</td>        <td>value 5</td>        <td>value 6</td>        <td>value 7</td>        <td>value 8</td>    </tr>    <tr>        <td colspan="5">            <!-- additional custom info is here (for Record 2) -->          </td>    </tr>    <tr>        <td>Record 3</td>        <td>value 9</td>        <td>value 10</td>        <td>value 11</td>        <td>value 12</td>    </tr>    <tr>        <td colspan="5">            <!-- additional custom info is here (for Record 3) -->          </td>    </tr></table>
```

  
**JS**  

```
<script type="text/javascript" src="jExpand.js"></script>$('#example_table').jExpand();(function($){    $.fn.jExpand = function(){        var element = this;        $(element).find("tr:odd").addClass("odd");        $(element).find("tr:not(.odd)").hide();        $(element).find("tr:first-child").show();        $(element).find("tr.odd").click(function() {            $(this).next("tr").toggle();        });           }   })(jQuery);
```

  
[ДЕМО](https://dev.xfor.top/go/aHR0cDovL3d3dy5zY3JpcHQtdHV0b3JpYWxzLmNvbS9kZW1vcy80MDYv) [СКАЧАТЬ](https://dev.xfor.top/go/aHR0cDovL3d3dy5zY3JpcHQtdHV0b3JpYWxzLmNvbS9kZW1vcy80MDYvc291cmNlczQwNi56aXA%3D)
