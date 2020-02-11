## menu.set1cIngredientId: Изменение id товара в системе 1С

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.set1cIngredientId'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$ingredient = [
    'id' => [
        [
            'ingredient_id' => 48,
            'id_1c'         => 'b80ffc81-0fc9-11e7-9ab4-ace01035e460',
        ],
    ],
];

$data = sendRequest($url, 'post', $ingredient);
```

> Пример ответа:

```json
{  
  "success":1
}
```

Метод изменяет id ингредиета в системе 1С

### HTTP запрос

`GET https://joinposter.com/api/menu.set1cIngredientId`

### POST-параметры запроса menu.set1cIngredientId

Параметр | Описание
-------- | --------
id | Массив из объектов

В свою очередь, каждый объект должен содержать следующие свойства:

Параметр | Описание
-------- | --------
ingredient_id | Id ингредиета
id_1c | Id ингредиета в системе 1С

### Параметры ответа menu.set1cIngredientId

Параметр | Описание
-------- | --------
success | 1, если id ингредиета в системе 1С успешно изменён
