---
title: "Laravel создание бекапа в Google Drive"
categories: 
  - "php"
---

Устанавливаем  

```
composer require spatie/laravel-backup
```

  
Добавляем в провайдеры  

```
'providers' => [
     ...
     Spatie\\Backup\\BackupServiceProvider::class
]
```

  
Публикуем конфиг  

```
$ php artisan vendor:publish --provider="Spatie\\Backup\\BackupServiceProvider"
```

  
Создаем расписание для бэкапа  

```
$schedule->command('backup:clean')->dailyAt('01:30');
$schedule->command('backup:run --only-db')->dailyAt('01:35');
```

  
Правим app/backup.php  

```
'disks' => [
    'google',                
    'local',             
],
```

  
Устанавливаем flysystem адаптер  

```
composer require nao-pon/flysystem-google-drive:~1.1
```

  
Создаем новый сервиспровайдер  

```
php artisan make:provider GoogleDriveServiceProvider
```

  
В boot() сексию этого сервиспровайдера дописываем  

```
\\Storage::extend('google', function ($app, $config) {
    $client = new \\Google_Client();
    $client->setClientId($config['clientId']);
    $client->setClientSecret($config['clientSecret']);
    $client->refreshToken($config['refreshToken']);
    $service = new \\Google_Service_Drive($client);
    $adapter = new \\Hypweb\\Flysystem\\GoogleDrive\\GoogleDriveAdapter($service, $config['folderId']);
    return new \\League\\Flysystem\\Filesystem($adapter);
});
```

  
Регистрируем в config/app.php этот сервис провайдер GoogleDriveServiceProvider  
В конфиг config/filesystems.php прописуем  

```
return [
  
    // ...
    
    'disks' => [
        
        // ...
        
        'google' => [
            'driver' => 'google',
            'clientId' => env('GOOGLE_DRIVE_CLIENT_ID'),
            'clientSecret' => env('GOOGLE_DRIVE_CLIENT_SECRET'),
            'refreshToken' => env('GOOGLE_DRIVE_REFRESH_TOKEN'),
            'folderId' => env('GOOGLE_DRIVE_FOLDER_ID'),
        ],
        
        // ...
        
    ],
    
    // ...
];
```

  
Правим файл окружения .env и добавляем  

```
GOOGLE_DRIVE_CLIENT_ID=xxx.apps.googleusercontent.com
GOOGLE_DRIVE_CLIENT_SECRET=xxx
GOOGLE_DRIVE_REFRESH_TOKEN=xxx
GOOGLE_DRIVE_FOLDER_ID=null
```

  
  
С ларавелом закончили, дальше заходим в https://console.developers.google.com/  
Создаем новый проект, выберем Drive API  
Заполняем  

[![Laravel создание бекапа в Google Drive](images/1*ObB4MuuH1gzKusw5wFk-bg.png "Laravel создание бекапа в Google Drive")](https://cdn-images-1.medium.com/max/1600/1*ObB4MuuH1gzKusw5wFk-bg.png)

  
Все  
Проверить работает ли все можно командой  

```
backup:run --only-db
```
