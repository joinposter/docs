## access.updateSpot: Изменение свойств заведения

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/access.updateSpot'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$spot = [
    'spot_id'   => 2,
    'spot_name' => 'Изменённое заведение',
];

$data = sendRequest($url, 'post', $spot);
```

> Пример ответа:

```json
{  
  "response":2
}
```

Метод изменяет свойства заведения

### HTTP POST запрос

`https://joinposter.com/api/access.updateSpot`

### POST-параметры запроса access.updateSpot

Параметр | Описание
-------- | --------
spot_id | Id заведения
spot_name | Название заведения

### Параметры ответа access.updateSpot

Параметр | Описание
-------- | --------
response | Id изменённого заведения
