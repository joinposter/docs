## access.createSpot: Создание заведения

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/access.createSpot'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$spot = [
    'spot_name' => 'Новое заведение',
];

$data = sendRequest($url, 'post', $spot);
```

> Пример ответа:

```json
{  
  "response":2
}
```

Метод создаёт заведение

### HTTP POST запрос

`https://joinposter.com/api/access.createSpot`

### POST-параметры запроса access.createSpot

Параметр | Описание
-------- | --------
spot_name | Название заведения

### Параметры ответа access.createSpot

Параметр | Описание
-------- | --------
response | Id созданного заведения
