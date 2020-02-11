## menu.getWorkshop: Свойства цеха

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.getWorkshop'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&workshop_id=1';

$data = sendRequest($url);
```

> Пример ответа:

```json
{  
  "response":{  
    "workshop_id":"1",
    "workshop_name":"Бар",
    "delete":"0"
  }
}
```

Метод возвращает свойства цеха

### HTTP запрос

`GET https://joinposter.com/api/menu.getWorkshop`

### GET-параметры запроса menu.getWorkshop

Параметр | Описание
-------- | --------
workshop_id | Id цеха

### Параметры ответа menu.getWorkshop

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит объект, внутри которого есть следующие параметры:

Параметр | Описание
-------- | --------
workshop_id | Id цеха
workshop_name | Название цеха
delete | Признак, удалён ли цех: 0 — не удалён, 1 — удалён
