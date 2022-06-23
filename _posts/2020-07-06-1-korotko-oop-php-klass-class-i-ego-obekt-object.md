---
title: "1. Коротко ООП PHP - Класс (class) и его объект (object)"
categories: 
  - "php"
---

Класс – это способ описания сущности. И по классу создается объект (экземпляр класса).  
Если абстрогироваться еще больше, то класс - это чертеж автомобиля, а обьект - это сам автомобиль собраный по чертежу. Рассмотрим пример.  

```php
<?php
class Car
{
    // константы
    const DOORS = 5;
    const TYPE = 'хетчбек';

    // свойства
    public $fuel = 100;
    public $speed = 0;
    public $odo;
    public $status = 'хорошее';

    // метод run ( имеет входные параметры скорость и время )
    public function run($speed = 0, $time = 0)
    {
        // $this это обращение к переменной или методу в контексте класса
        $this->speed = $speed;
        $this->odo = $speed * $time;
        return 'Движемся со скоростью: ' . $speed . ' км/ч. В течении ' . $time . ' часов';
    }

    // метод stop
    public function stop()
    {
        $this->speed = 0;
        return 'Остановились, наша скорость: 0 км/ч';
    }

    // метод getOdo
    public function getOdo()
    {
        return 'Проехали дистанцию: ' . $this->odo . ' км';
    }

}

// Cоздаем экземпляр объекта класса Car
$car = new Car();

// Вызов констант
echo 'У машины: ' . $car::DOORS . ' дверей<br/>';
echo 'Тип машины: ' . $car::TYPE . ' <hr/>';

// Текущие свойства
echo 'В баке: ' . $car->fuel . ' л топлива<br/>';

// Операция над свойством
$car->fuel = $car->fuel / 2; // Слили половину =)
echo 'Теперь в баке: ' . $car->fuel . ' л топлива<br/>';
echo 'Текущая скорость машины: ' . $car->speed . ' км/ч<hr/>';

// Выполнение методов
echo $car->run() . '<br/>';
echo $car->run(60, 10) . '<br/>';
echo $car->stop() . '<br/>';
echo $car->getOdo();
```
