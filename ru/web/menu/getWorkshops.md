## menu.getWorkshops: Список цехов

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.getWorkshops'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Пример ответа:

```json
{  
  "response":[  
    {  
      "workshop_id":"1",
      "workshop_name":"Бар",
      "delete":"0"
    },
    {  
      "workshop_id":"2",
      "workshop_name":"Кухня",
      "delete":"0"
    },
    {  
      "workshop_id":"3",
      "workshop_name":"Кондитерская",
      "delete":"0"
    },
    {  
      "workshop_id":"4",
      "workshop_name":"Кальян",
      "delete":"0"
    }
  ]
}
```

Метод возвращает список цехов

### HTTP запрос

`GET https://joinposter.com/api/menu.getWorkshops`

### Параметры ответа menu.getWorkshops

Параметр | Описание
-------- | --------
response | Массив объектов

Внутри параметра `response` лежит массив, в каждом элементе которого есть следующие параметры:

Параметр | Описание
-------- | --------
workshop_id | Id цеха
workshop_name | Название цеха
delete | Признак, удалён ли цех: 0 — не удалён, 1 — удалён
