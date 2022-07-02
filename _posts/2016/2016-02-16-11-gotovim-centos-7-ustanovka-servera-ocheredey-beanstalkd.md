---
title: "11 - Готовим CentOS 7. Установка сервера очередей beanstalkd"
date: "2016-02-16"
categories: 
  - "note"
---

<iframe title="YouTube video player" width="840" height="473" src="https://www.youtube.com/embed/sZj6enU1FRc?rel=0&amp;wmode=transparent" frameborder="0" allowfullscreen></iframe>

Устанавливаем git

```
yum install git -y
cd /tmp
```

Клонируем репозиторий

```
git clone git://github.com/kr/beanstalkd.git
cd beanstalkd
make
cp beanstalkd /usr/bin/beanstalkd
mkdir /var/lib/beanstalkd
```

Создаем скрипт автозапуска

```
nano -w /etc/systemd/system/beanstalkd.service
```

```
[Unit]
Description=Beanstalkd is a simple, fast work queue

[Service]
User=root
ExecStart=/usr/bin/beanstalkd -b /var/lib/beanstalkd

[Install]
WantedBy=multi-user.target
```

Запускаем и добавляем в автозагрузку

```
systemctl start beanstalkd
systemctl enable beanstalkd
```

Проверяем

```
systemctl status beanstalkd
ps ax | grep beanstalkd
```

Удостоверимся на практике что сервер очередей работает

Установим композер

```
cd /tmp
curl -sS https://getcomposer.org/installer | php70
mv composer.phar /usr/local/bin/composer
```

Установим pheanstalk

```
cd /var/www/test.dev
php70 /usr/local/bin/composer require pda/pheanstalk
```

Создадим клиента

```
nano -w /var/www/test.dev/producer.php
```

```
<?php
require_once './vendor/autoload.php';
use Pheanstalk\\Pheanstalk;
$pheanstalk = new Pheanstalk('127.0.0.1');
$data = serialize(
	array(
		'do' => 'data',
		'msg' => "job 7 payload goes here\\n"
	)
);
$pheanstalk->useTube('default')->put($data);
echo 'added';
```

Создадим воркер который будет зписывать в файлик наши задачи

```
nano -w /var/www/test.dev/worker.php
```

```
<?php
require_once './vendor/autoload.php';
use Pheanstalk\\Pheanstalk;
$pheanstalk = new Pheanstalk('127.0.0.1');
while(1) {
	$job = $pheanstalk->watch('default')->reserve();
	if ( $job->getData() ) {
		$data = unserialize($job->getData());
		if ( $data['do'] == 'data' ) {
			$file = 'data.txt';
			$current = file_get_contents($file);
			$current .= $data['msg'];
			file_put_contents($file, $current);
			echo 'Log: add data'. PHP_EOL;		
		}
		$pheanstalk->delete($job);		
	}
}
```

Запустим наш воркер

```
cd /var/www/test.dev
php70 worker.php
```

Заходим через наш бразуер на http://test.dev/producer.php и клацаем обновить можно менять job-ы, что бы удостовериться что в очередь попадают разные задачи а не одна и та же, и в нашем файлике data.txt проверяем, что все что передано, отправлено в файлик.

Почему Beanstalkd - это сервер очередей, написаный на С, он маленький и простой. И мониторятся очереди.

Сервер — это сам Beanstalkd, который принимает job-ы от клиента Продюсер(клиент) — это основное PHP приложение, которое отправляет job-ы на сервер Воркер — это PHP скрипт, который получает сообщение с сервера задач и выполняет какие-то действия

Что за job? Job (задание) — это любая информация, которую клиент отправляет на сервер очередей. Потом эта же информация передается на обработчик (воркер). К примеру, мы хотим отправить почту на сервер очередей, то создаем для него задачу: отправка почты - адрес получаетля, заголовок письма, тело письма.

Задача 1 - он должен запускаться только из консоли Задача 2 - должен выключаться если сам воркер изменился ( запускать его будет супервизор (об этом будет позже) ) Задача 3 - собственно обрабатывать наши задачи из очереди Используется https://github.com/pda/pheanstalk

```
<?php
require_once ENGINE_DIR . '/assets/vendor/autoload.php';
use Pheanstalk\\Pheanstalk;
if ( isCommandLine() != true ) {
	header("HTTP/1.0 404 Not Found");
	header('Location: /404');
	die();
}
function isCommandLine() {
   return defined('STDIN');
}
function get_changed_time() {
	$fp = fopen(__FILE__, "r");
	$fstat = fstat($fp);
	$res = $fstat['mtime'];
	return $res;
}
function check_changed_time($changed_time) {
	$time = get_changed_time();
	if ($time !== $changed_time){
		echo "File has been changed!";
		exit(1);
	}		
}
$pheanstalk = new Pheanstalk('127.0.0.1');
$mail = new PHPMailer;
$changed_time = get_changed_time();
while(1) {
	// проверяем не изменился ли наш воркер
	check_changed_time($changed_time);
	// смотрим наш tube default не появилось ли в нем задач, если нет ничего не делаем.
	$job = $pheanstalk->watch('default')->reserve();
	if ( !isset($job) OR !$job ) {
		// return FALSE;
	} else {
		// распаковываем ранее запакованные данные
		$data = unserialize($job->getData());
		// и тд и тп =)
	}
} 
```

Beanstalk console - Административная консоль для сервера очередей Beanstalk, написанная на PHP Возможности - Общий список серверов в конфиге для всех пользователей - Глобальный список серверов может быть установлен через переменную окружения BEANSTALK\_SERVERS - Каждый пользователь может добавить свой персональный сервер - Полный список доступных труб - Полная статистика тасков в трубах - Realtime-обновление с подсветкой изменившихся значений - Вы можете просматривать таски в каждой трубе (ready/delayed/buried) - Вы можете выполнять операции с тасками в каждой трубе (add/kick/delete) [https://github.com/ptrofimov/beanstalk\_console](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL3B0cm9maW1vdi9iZWFuc3RhbGtfY29uc29sZQ%3D%3D)
