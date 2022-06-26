---
title: "soap-client - soap клиент на чистом php"
date: ""
categories: 
  - "php"
---

Пример использования  

```
// composer auto loader
require __DIR__ . '/vendor/autoload.php';

// instantiate the main container class
// the name was defined by --dest-class=GlobalWeather/Container/SoapClientContainer
// parameter during the generation process
$container = new SoapClientContainer();

// create a JMS serializer instance
$serializer = SoapContainerBuilder::createSerializerBuilderFromContainer($container)->build();
// get the metadata from the container
$metadata = $container->get('goetas.soap_client.metadata_reader');

$factory = new ClientFactory($metadata, $serializer);

/**
 * @var $client \\GlobalWeather\\SoapStubs\\WeatherSoap
 */
 // get the soap client
$client = $factory->getClient('http://www.webservicex.net/weather.asmx?WSDL');

// call the webservice
$result = $client->getWeather(2010, "May", "USA");
```

  
[https://github.com/goetas-webservices/soap-client](https://dev.xfor.top/go/aHR0cHM6Ly9naXRodWIuY29tL2dvZXRhcy13ZWJzZXJ2aWNlcy9zb2FwLWNsaWVudA%3D%3D)
