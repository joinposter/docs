## spots.getSpotTablesHalls: Список залов

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/spots.getSpotTablesHalls'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Пример ответа:

```json
{  
  "response":[  
    {  
      "hall_id":"3",
      "hall_name":"Зал в кафе на Полянке",
      "hall_order":"1",
      "spot_id":"1",
      "delete":"0",
      "last_modified_time":"2017-06-22 13:54:58"
    },
    {  
      "hall_id":"5",
      "hall_name":"Зал у львівській кав&#39;ярні",
      "hall_order":"2",
      "spot_id":"2",
      "delete":"0",
      "last_modified_time":"2017-06-22 13:54:58"
    }
  ]
}
```

Метод возвращает список залов

### HTTP запрос

`GET https://joinposter.com/api/spots.getSpotTablesHalls`

### Параметры ответа spots.getSpotTablesHalls

Параметр | Описание
-------- | --------
response | Массив объектов

Внутри параметра `response` лежит массив, в каждом элементе которого есть следующие параметры:

Параметр | Описание
-------- | --------
hall_id | Id зала
hall_name | Название зала
hall_order | Порядок залов
spot_id | Id заведения
delete | Признак, что зал удалён: 0 — не удалён, 1 — удалён
last_modified_time | Время последнего изменения свойств зала
