---
title: "12.  Коротко ООП PHP - Примеры"
date: ""
categories: 
  - "php"
---

**Шаблон фасад**

![12. Коротко ООП PHP - Примеры](images/1486816992_diag.png "12. Коротко ООП PHP - Примеры")

Паттерн фасад определяет интерфейс более высокого уровня, который упрощает использование подсистем.

```
<?php
class Stringify {

 	public function __construct($str)
 	{
 		$this->str = $str;
 		$this->_AddText();
 		$this->_AddDigits();
 		$this->_AddObject(new Stuff);
 		echo $this->str;
 	}

 	private function _AddText()
 	{
		$this->str .= ' | Adding Text';
 	}

 	private function _AddDigits()
 	{
		$this->str .= ' | Adding Ditgits: 402 ';
 	}

 	private function _AddObject(Stuff $stuff)
 	{
		$this->str .= $stuff->WriteCrap();
 	}

}

class Stuff
{
	public function WriteCrap()
	{
		return __CLASS__ . ' Writing Stuff';
	}
}

new Stringify('Intro Text');
```

  
**Шаблон декоратор**

![12. Коротко ООП PHP - Примеры](images/1486817180_logo.png "12. Коротко ООП PHP - Примеры")

  
Сущность работы паттерна декоратор заключается в \\"оборачивании\\" готового объекта новым функционалом, при этом весь оригинальный интерфейс объекта остается доступным (декоратор переадресует все запросы объекту).  

```
<?php

class Player
{

	public $Data = array();

	public function __construct(array $info)
	{
		$this->Data = $info;
	}

}

abstract class Player_Decorater
{
	abstract public function Add($int);
}

class Player_Str_Decorate extends Player_Decorater
{
	public function __construct(Player $p)
	{
		$this->Player = $p;
		$this->Player->Data['str'] += 5;
	}
	public function Add($int)
	{
		$this->Player->Data['str'] += $int;
	}
}

class Player_Dex_Decorate extends Player_Decorater
{
	public function __construct(Player $p)
	{
		$this->Player = $p;
		$this->Player->Data['dex'] += 25;
	}
	public function Add($int)
	{
		$this->Player->Data['dex'] += $int;
	}
}

$P = new Player(array('str' => 10, 'dex' => 20));
echo $P->Data['str'];
echo $P->Data['dex'];

echo '<hr/>';

$Str = new Player_Str_Decorate($P);
echo $Str->Player->Data['str'];

$Dex = new Player_Dex_Decorate($P);
$Dex->Add(55);
echo $Dex->Player->Data['dex'];
```

  
**Цепочка методов**

```
class Cupcake
{

	public $Cupcake = array();

	public function Frosting($str)
	{
		$this->Cupcake['Frosting'] = $str;
		return $this;
	}

	public function Nuts($int)
	{
		$this->Cupcake['Nuts'] = (int)$int;
		return $this;
	}

	public function Sprinkles($int)
	{
		$this->Cupcake['Sprinkles'] = (int)$int;
		return $this;
	}

}

$cupcake = new Cupcake();

$cupcake->Nuts('10')->Frosting('chocolate')->Sprinkles('200');

print_r($cupcake->Cupcake);
```
