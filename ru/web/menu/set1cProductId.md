## menu.set1cProductId: Изменение id товара в системе 1С

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.set1cProductId'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$products = [
    'id' => [
        [
            'product_id' => 48,
            'id_1c'      => 'b80ffc81-0fc9-11e7-9ab4-ace01035e460',
        ],
    ],
];

$data = sendRequest($url, 'post', $products);
```

> Пример ответа:

```json
{  
  "success":1
}
```

Метод изменяет id товара в системе 1С

### HTTP запрос

`GET https://joinposter.com/api/menu.set1cProductId`

### POST-параметры запроса menu.set1cProductId

Параметр | Описание
-------- | --------
id | Массив объектов

В свою очередь, каждый объект должен содержать следующие свойства:

Параметр | Описание
-------- | --------
product_id | Id товара
id_1c | Id товара в системе 1С

### Параметры ответа menu.set1cProductId

Параметр | Описание
-------- | --------
success | 1, если id товара в системе 1С успешно изменён
