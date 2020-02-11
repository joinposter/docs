## spots.set1cSpotsId: Изменение id заведений в системе 1С

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/spots.set1cSpotsId'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$spots = [
    'id' => [
        [
            'spot_id' => 32,
            'id_1c'   => 'b80ffc81-0fc9-11e7-9ab4-ace01035e460',
        ],
    ],
];

$data = sendRequest($url, 'post', $spots);
```

> Пример ответа:

```json
{  
  "success":1
}
```

Метод изменяет id заведений в системе 1С

### HTTP запрос

`GET https://joinposter.com/api/spots.set1cSpotsId`

### POST-параметры запроса spots.set1cSpotsId

Параметр | Описание
-------- | --------
id | Массив объектов

В свою очередь, каждый объект должен содержать следующие свойства:

Параметр | Описание
-------- | --------
spot_id | Id заведения
id_1c | Id заведения в системе 1С

### Параметры ответа spots.set1cSpotsId

Параметр | Описание
-------- | --------
success | 1, если id заведений в системе 1С успешно изменены
