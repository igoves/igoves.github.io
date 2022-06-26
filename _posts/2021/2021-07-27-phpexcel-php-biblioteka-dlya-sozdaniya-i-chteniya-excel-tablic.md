---
title: "PHPExcel - php библиотека для создания и чтения excel таблиц"
date: ""
categories: 
  - "php"
---

На текущий момент поддерживает Excel (BIFF) .xls, Excel 2007 (OfficeOpenXML) .xlsx, CSV, Libre/OpenOffice Calc .ods, Gnumeric, PDF, HTML.  

```
// Add some data, we will use printing features
echo date('H:i:s') , " Add some data" , EOL;
for ($i = 1; $i < 200; $i++) {
	$objPHPExcel->getActiveSheet()->setCellValue('A' . $i, $i);
	$objPHPExcel->getActiveSheet()->setCellValue('B' . $i, 'Test value');
}
```

  
[https://github.com/PHPOffice/PHPExcel](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL1BIUE9mZmljZS9QSFBFeGNlbA%3D%3D)
