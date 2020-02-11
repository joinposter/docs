## menu.createWorkshop: Создание цеха

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.createWorkshop'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$workshop = [
    'workshop_name' => 'Мангал',
];

$data = sendRequest($url, 'post', $workshop);
```

> Пример ответа:

```json
{  
  "response":5
}
```

Метод создаёт цех

### HTTP запрос

`GET https://joinposter.com/api/menu.createWorkshop`

### POST-параметры запроса menu.createWorkshop

Параметр | Описание
-------- | --------
workshop_name | Обязательный параметр, название цеха

### Параметры ответа menu.createWorkshop

Параметр | Описание
-------- | --------
response | Id созданного цеха
