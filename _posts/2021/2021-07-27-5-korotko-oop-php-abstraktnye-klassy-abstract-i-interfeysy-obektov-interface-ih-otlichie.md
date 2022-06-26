---
title: "5. Коротко ООП PHP - Абстрактные классы (abstract) и интерфейсы объектов (interface), их отличие"
date: ""
categories: 
  - "php"
---

Методы, объявленные абстрактными, несут, по существу, лишь описательный смысл и не могут включать реализации. При наследовании от абстрактного класса, все методы, помеченные абстрактными в родительском классе, должны быть определены в классе-потомке; кроме того, область видимости этих методов должна совпадать (или быть менее строгой).  
Интерфейсы объектов позволяют создавать код, который указывает, какие методы должен реализовать класс, без необходимости описывания их функционала. Тела методов интерфейсов должны быть пустыми.  
Интерфейс - это абстрактный класс, у которого все методы не реализованы, все публичные и нет переменных класса.  
Абстрактный класс - это как ЗАГОТОВКА.  
Интерфейс - это как КОНТРАКТ, что обязан выполнять класс.  
А теперь в чем же отличие:  
\- Интерфейсы, в отличии от абстрактных классов, поддерживают множественное наследование. Т.е. класс-потомок может реализовывать 2 или более интерфейсов одновременно: class A implements Int1, Int2, но class A extends AbstrB  
\- Интерфейс содержит исключительно объявления методов, но не содержит реализации.  
\- Интерфейс не может включать в себя свойства  
\- Класс-потомок обязан реализовывать все методы интерфейса  
\- В интерфейсе все методы открытые  
**abstract**  

```
<?php

abstract class Car {
	public $x;
	public $y;

    public function __construct($x, $y) {
      $this->x = $x;
      $this->y = $y;
    }
	
	abstract public function move ($x, $y);

}

class BMW extends Car {
	
    public function move($x, $y) {
		echo "Движение BMW из координат ($this->x, $this->y) в координаты ($x, $y)<br />";
		$this->x = $x;
		$this->y = $y;
    }
	
}

$auto = new BMW(10, 20);
echo $auto->x;
echo "<br />";
echo $auto->y;
echo "<br />";
$auto->move(5, 15);
```

**interface**

```
<?php

interface Parsed {
	public function Parsed($blah);
}

interface DotSyntax {
	public function UsesDotSyntax();
}

interface Compiled {
	public function isCompiled();
}



class Java implements DotSyntax, Compiled {
	public function __construct() {
		echo 'Java was created<br/>';
		$this->UsesDotSyntax();
		$this->isCompiled();
	}

	public function UsesDotSyntax() {
		echo 'Yes, UsesDotSyntax<br/>';
	}

	public function isCompiled() {
		echo 'Yes, isCompiled<br/>';
	}
}

class PHP implements Parsed {
	public function __construct() {
		echo 'PHP was created<br/>';
		$this->Parsed('Yes, Parsed<br/>');
	}
	public function Parsed($blah) {
		echo $blah;
	}
}

$php = new PHP();
$java = new Java();
```
