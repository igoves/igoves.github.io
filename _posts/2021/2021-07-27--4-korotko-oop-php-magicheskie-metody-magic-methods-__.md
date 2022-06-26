---
title: "4. Коротко ООП PHP - Магические методы (magic methods) __"
date: ""
categories: 
  - "php"
---

Магиеские методы - \\"магия\\" данных методов сводится к тому, что они могут перехватывать (отсюда их второе название - методы-перехватчики) сообщения, посланные неопределенным (по сути - несуществующим) методам и свойствам  
Всегда начинаются с двойного подчеркивания.  
**\_\_construct()** - этот метод запускается автоматически при созданнии экземпляра класса  
**\_\_destruct()** - метод запускается автоматически при уничтожении обьекта  
**\_\_call(), \_\_callStatic()** - перехватывают обращение к несуществующему методу в контексте объекта и в статическом контексте  
**\_\_get(), \_\_set()** - выполняется при чтении/записи данных из недоступных свойств  
**\_\_isset()** - будет выполнен при использовании isset() или empty() на недоступных свойствах  
**\_\_unset()** - будет выполнен при вызове unset() на недоступном свойстве  
**\_\_sleep()** - вызывается, когда объект подвергается сериализации при помощи функции serialize()  
**\_\_wakeup()** - вызывается при восстановлении объекта при помощи функции unserialize()  
**\_\_toString()** - метод, с помощью которого можно обращаться к классу как к строке  
**\_\_invoke()** - вызывается при попытке использовать объект в качестве функции  
**\_\_set\_state()** - метод, который вызывается для классов, экспортирующих значения свойств функцией var\_export()  
**\_\_clone()** - вызывается при клонировании объекта  
**\_\_debugInfo()** - метод вызывается функцией var\_dump(), когда необходимо вывести список свойств объекта  

```
<?php
class Car {

	function __construct() {
		echo 'Конструктор, вызывается автоматически во время создания экземпляра класса <br/>';
	}

	function __destruct() {
		echo 'Деструктор, вызывается автоматически во время уничтожения экземпляра класса <br/>';
	}

    function __call($name, $arguments) {
        // значение $name регистрозависимо
        echo "Вызов метода '$name' " . implode(', ', $arguments). "<br/>";
    }

    static function __callStatic($name, $arguments) {
        echo "Вызов статического метода '$name' " . implode(', ', $arguments). "<br/>";
    }

	function __get($param) {
		echo "Выполнить из за чтения данных из недоступных свойств: $param <br/>";
	}
	
	function __set($name, $value) {
		echo "Выполнить метод из за записи данных в недоступные свойства: $name -> $value <br/>";
		return $this->{$name} = $value; 
	}

    function __isset($name) {
        echo "Установлено ли '$name'? <br/>";
        // return isset($this->data[$name]);
    }

    function __unset($name) {
        echo "Уничтожение '$name' <br/>";
        // unset($this->data[$name]);
    }
	
	function __sleep() {
		echo "Объект подвергается сериализации при помощи функции serialize <br/>";
    }	
	
	// function __wakeup() {
		// echo "Объект подвергается восстановлении при помощи функции unserialize <br/>";
    // }	
	
	function __toString() {
		return "Мы вызвали " . __METHOD__ . "<br/>";
	}
	
	function __invoke($vars) {
		return "Нельзя вызывать класс как функцию <br/>";
	}
	
	function __set_state($an_array) {
		return print_r($an_array) . "<br/>";
	}

	function __clone()	{
		echo 'Вызывается при клонировании объекта <br/>';
	}

	function __debugInfo() {
		echo 'Вызывается при var_dump <br/>';
	}
	
}

$car = new Car();	// __construct
$car->runTest('в контексте объекта');	// __call
car::runTest('в статическом контексте объекта'); // __callStatic
$car->asdfasdf;	// __get
$car->asdfasdf = 'test';	// __set
isset($car->a); // __isset
isset($car->b); // __unset
$a = serialize($car); // __sleep
// unserialize($a); // __wakeup
echo $car; // __toString
echo $car('Пиу'); // __invoke
eval('$b = ' . var_export($car, true) . ';'); 
var_dump($b); // __set_state
$car2 = clone $car; // __clone
var_dump($car2); // __debugInfo
```
