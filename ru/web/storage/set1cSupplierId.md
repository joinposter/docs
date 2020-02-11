## storage.set1cSupplierId: Изменение id поставщиков в системе 1С

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/storage.set1cSupplierId'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$supplier = [
    'id' => [
        [
            'supplier_id' => 32,
            'id_1c'   => 'b80ffc81-0fc9-11e7-9ab4-ace01035e460',
        ],
    ],
];

$data = sendRequest($url, 'post', $supplier);
```

> Пример ответа:

```json
{  
  "success":1
}
```

Метод изменяет id поставщиков в системе 1С

### HTTP запрос

`GET https://joinposter.com/api/storage.set1cSupplierId`

### POST-параметры запроса storage.set1cSupplierId

Параметр | Описание
-------- | --------
id | Массив объектов

В свою очередь, каждый объект должен содержать следующие свойства:

Параметр | Описание
-------- | --------
supplier_id | Id поставщика
id_1c | Id поставщика в системе 1С

### Параметры ответа storage.set1cSupplierId

Параметр | Описание
-------- | --------
success | 1, если id поставщика в системе 1С успешно изменены
