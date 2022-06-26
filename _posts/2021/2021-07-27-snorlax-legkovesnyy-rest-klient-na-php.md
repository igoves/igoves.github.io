---
title: "snorlax - легковесный REST клиент на php"
date: ""
categories: 
  - "php"
---

Пример использования  

```
<?php

use Snorlax\\Resource;
use Snorlax\\RestClient;

class PokemonResource extends Resource
{
    public function getBaseUri()
    {
        // You don't want a raw value like this, use an environment variable :)
        return 'http://localhost/api/pokemons';
    }

    public function getActions()
    {
        return [
            'all' => [
                'method' => 'GET',
                'path' => '/',
            ],
            'get' => [
                'method' => 'GET',
                'path' => '/{0}.json',
            ],
            'create' => [
                'method' => 'POST',
                'path' => '/',
            ],
        ];
    }
}

$client = new RestClient([
    'resources' => [
        'pokemons' => PokemonResource::class,
    ],
]);

// GET http://localhost/api/pokemons?sort=id:asc
$response = $client->pokemons->all([
    'query' => [
        'sort' => 'id:asc',
    ],
]);

// GET http://localhost/api/pokemons/143.json?fields=id,name
$response = $client->pokemons->get(143, [
    'query' => [
        'fields' => 'id,name',
    ],
]);

// POST http://localhost/api/pokemons
$response = $client->pokemons->create([
    'body' => [
        'name' => 'Bulbasaur',
    ],
]);
```

  
[https://github.com/ezdeliveryco/snorlax](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2V6ZGVsaXZlcnljby9zbm9ybGF4)
