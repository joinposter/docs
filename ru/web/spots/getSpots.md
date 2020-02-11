## spots.getSpots: Список заведений

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/spots.getSpots'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Пример ответа:

```json
{  
   "response":[  
      {  
         "spot_id":1,
         "name":"Кафе на Полянке",
         "address":"Москва, ул. Б.Полянка 44"
      },
      {  
         "spot_id":2,
         "name":"Львовська Кав'ярня",
         "address":"Львов, пл. Ринок, 11"
      }
   ]
}
```

Метод возвращает список заведений

### HTTP запрос

`GET https://joinposter.com/api/spots.getSpots`

### Параметры ответа spots.getSpots

Параметр | Описание
-------- | --------
response | Массив объектов

Внутри параметра `response` лежит массив, в каждом элементе которого есть следующие параметры:

Параметр | Описание
-------- | --------
spot_id | Id заведения
name | Название заведения
address | Адрес заведения

