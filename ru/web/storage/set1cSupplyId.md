## storage.set1cSupplyId: Изменение id поставок в системе 1С

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/storage.set1cSupplyId'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$supply = [
    'id' => [
        [
            'supply_id' => 32,
            'id_1c'   => 'b80ffc81-0fc9-11e7-9ab4-ace01035e460',
        ],
    ],
];

$data = sendRequest($url, 'post', $supply);
```

> Пример ответа:

```json
{  
  "success":1
}
```

Метод изменяет id поставок в системе 1С

### HTTP запрос

`GET https://joinposter.com/api/storage.set1cSupplyId`

### POST-параметры запроса storage.set1cSupplyId

Параметр | Описание
-------- | --------
id | Массив объектов

В свою очередь, каждый объект должен содержать следующие свойства:

Параметр | Описание
-------- | --------
supply_id | Id поставки
id_1c | Id поставщика в системе 1С

### Параметры ответа storage.set1cSupplyId

Параметр | Описание
-------- | --------
success | 1, если id поставки в системе 1С успешно изменены
