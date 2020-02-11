## application.changeTariff: Изменение тарифного плана приложения

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/application.changTariff'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$tariff = [
    "tariff_key"   => "shop"
];

$data = sendRequest($url, 'post', $tariff);

```

> Пример ответа:

```json
{
   "response":true
}
```

Метод меняет тарифный план вашего приложения подключенного клиенту Poster

### HTTP POST запрос

`POST https://joinposter.com/api/application.changTariff`


### POST-параметры запроса application.changTariff

Параметр | Описание
-------- | --------
tariff_key | Уникальный ключ нового тарифа на который меняем. Ключи тарифов выдаются при публикации приложения в каталоге. 


### Параметры ответа application.changTariff

Параметр | Описание
-------- | --------
response | Результат запроса, `true` — если запрос выполнен успешно
