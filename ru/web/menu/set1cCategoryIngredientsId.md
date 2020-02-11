## menu.set1cCategoryIngredientsId: Изменение id категории ингредиентов в системе 1С

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.set1cCategoryIngredientsId'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$category_ingredients = [
    'id' => [
        [
            'category_id' => 3,
            'id_1c'       => 'b80ffc81-0fc9-11e7-9ab4-ace01035e460',
        ],
    ],
];

$data = sendRequest($url, 'post', $category_ingredients);
```

> Пример ответа:

```json
{  
  "success":1
}
```

Метод изменяет id категории ингредиентов в системе 1С

### HTTP запрос

`GET https://joinposter.com/api/menu.set1cCategoryIngredientsId`

### POST-параметры запроса menu.set1cCategoryIngredientsId

Параметр | Описание
-------- | --------
id | Массив из объектов

В свою очередь, каждый объект должен содержать следующие свойства:

Параметр | Описание
-------- | --------
category_id | Id категории ингредиентов
id_1c | Id категории ингредиентов в системе 1С

### Параметры ответа menu.set1cCategoryIngredientsId

Параметр | Описание
-------- | --------
success | 1, если id категории ингредиентов в системе 1С успешно изменён

