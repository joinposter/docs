## menu.removeWorkshop: Удаление цеха

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.removeWorkshop'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$workshop = [
    'workshop_id' => 2,
];

$data = sendRequest($url, 'post', $workshop);
```

> Пример ответа:

```json
{  
  "response":true
}
```

Метод удаляет цех

### HTTP запрос

`GET https://joinposter.com/api/menu.removeWorkshop`

### POST-параметры запроса menu.removeWorkshop

Параметр | Описание
-------- | --------
workshop_id | Id цеха

### Параметры ответа menu.removeWorkshop

Параметр | Описание
-------- | --------
response | true, если цех успешно удалён
