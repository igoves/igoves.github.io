---
title: "2. Коротко ООП PHP - Принципы: инкапсуляция, полиморфизм, наследование"
categories: 
  - "php"
---

Обьект Car в жизни это слишком обобщенно. Поэтому создадим машины унаследовав родитель-класс Car (наследование), имзеним их свойства и методы при необходимости (полиморфизм), и ограничим области видимости свойств и методов с помощью спецификаторов доступа private, protected, public ( инкапсуляция(сокрытие внутренних процессов)).  

```
<?php
class Car {

	const DOORS = 5;
	const TYPE = 'хетчбек';

	// инкапсуляция	(ограничили область видимости свойств odo только классом Car и его наследникми)
	protected $odo;
	
	public $fuel = 100;
	public $speed = 0;

	public function run( $speed = 0, $time = 0 ) {
		$this->speed = $speed;
		$this->odo = $speed*$time;
		return 'Движемся со скоростью: ' . $speed . ' км/ч. В течении '  .$time . ' часов <br/>';
	}

	public function stop() {
		$this->speed = 0;
		return 'Остановились, наша скорость: 0 км/ч <br/>' . $this->getOdo();
	}

	// инкапсуляция (ограничили область видимости метода getOdo только классом Car)
	private function getOdo () {
		return 'Проехали дистанцию: ' . $this->odo . ' км <br/>';
	}
	
}

// наследование (наследуем класс родитель Car)
class Zaz extends Car {
	
	// полиморфизм (переопределили константы DOORS и TYPE для Zaz)
	const DOORS = 4;
	const TYPE = 'седан';
	
	// полиморфизм (переопределили свойство $fuel)
	public $fuel = 40;

	// расширили новым методом zagloh только для класса Zaz 
	public function zagloh () {
		return 'Заглох... <br/>';
	}
	
}

// наследование (наследуем класс родитель Car)
class Amfibia extends Car {

	// полиморфизм (переопределили метод run, все остальное осталось от класса Car)
	public function run ( $speed = 0, $time = 0, $water = 0 ) {
		$this->speed = $water == 1? $speed/3 :	$speed;
		$this->odo = $this->speed*$time;
		return 'Движемся со скоростью: ' . $this->speed . ' км/ч. В течении '  .$time . ' часов <br/>';
	}
	
	// рашсирили родительский метод stop
	public function stop() {
		return 'Пшшшш... ' . parent::stop();
	}
	
}


// Cоздаем экземпляр объекта класса Zaz
$car = new Zaz();
echo 'У машины: ' . $car::DOORS . ' двери<br/>';
echo 'Тип машины: ' . $car::TYPE . '<br/>';
echo 'В баке: ' . $car->fuel . ' л топлива<br/>';
echo 'Текущая скорость машины: ' . $car->speed . ' км/ч<br/>';
echo $car->run();
echo $car->zagloh();
echo $car->run(60, 10);
echo $car->stop();

// Cоздаем экземпляр объекта класса Amfibia
$car2 = new Amfibia();
echo 'По воде: ' . $car2->run(60, 10, 1);
echo $car2->stop();
```
