## access.removeSpot: Удаление заведения

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/access.removeSpot'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$spot = [
    'spot_id' => 1,
];

$data = sendRequest($url, 'post', $spot);
```

> Пример ответа:

```json
{  
  "response":true
}
```

Метод удаляет заведение

### HTTP POST запрос

`https://joinposter.com/api/access.removeSpot`

### POST-параметры запроса access.removeSpot

Параметр | Описание
-------- | --------
spot_id | Id удаляемого заведения

### Параметры ответа access.removeSpot

Параметр | Описание
-------- | --------
response | `true`, если заведение успешно удалено
