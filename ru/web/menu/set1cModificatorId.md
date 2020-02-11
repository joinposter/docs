## menu.set1cModificatorId: Изменение id модификатора товара в системе 1С

>  Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.set1cModificatorId'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$product_modificators = [
    'id' => [
        [
            'modificator_id' => 7,
            'id_1c'          => 'b80ffc81-0fc9-11e7-9ab4-ace01035e460',
        ],
    ],
];

$data = sendRequest($url, 'post', $product_modificators);
```

> Пример ответа:

```json
{  
  "success":1
}
```

Метод изменяет id модификатора товара в системе 1С

### HTTP запрос

`GET https://joinposter.com/api/menu.set1cModificatorId`

### POST-параметры запроса menu.set1cModificatorId

Параметр | Описание
-------- | --------
id | Массив объектов

В свою очередь, каждый объект должен содержать следующие свойства:

Параметр | Описание
-------- | --------
modificator_id | Id модификатора товара
id_1c | Id модификатора товара в системе 1С

### Параметры ответа menu.set1cModificatorId

Параметр | Описание
-------- | --------
success | 1, если id модификатора товара в системе 1С успешно изменён
