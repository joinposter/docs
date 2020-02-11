## menu.set1cCategoryId: Изменение id категории товаров в системе 1С

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.set1cCategoryId'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$category = [
    'id' => [
        [
            'category_id' => 32,
            'id_1c'       => 'b80ffc81-0fc9-11e7-9ab4-ace01035e460',
        ],
    ],
];

$data = sendRequest($url, 'post', $category);
```

> Пример ответа:

```json
{  
  "success":1
}
```

Метод изменяет id категории товаров в системе 1С

### HTTP запрос

`GET https://joinposter.com/api/menu.set1cCategoryId`

### POST-параметры запроса menu.set1cCategoryId

Параметр | Описание
-------- | --------
id | Массив объектов

В свою очередь, каждый объект должен содержать следующие свойства:

Параметр | Описание
--------- | -----------
category_id | Id категории товаров
id_1c | Id категории товаров в системе 1С

### Параметры ответа menu.set1cCategoryId

Параметр | Описание
--------- | -----------
success | 1, если id категории товаров в системе 1С успешно изменён
