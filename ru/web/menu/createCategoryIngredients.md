## menu.createCategoryIngredients: Создание категории ингредиентов

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.createCategoryIngredients'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$category_ingredients = [
    'category_name' => 'Овощи',
];

$data = sendRequest($url, 'post', $category_ingredients);
```

> Пример ответа:

```json
{  
  "response":27
}
```

Метод создаёт категорию ингредиентов

### HTTP запрос

`GET https://joinposter.com/api/menu.createCategoryIngredients`

### POST-параметры запроса menu.createCategoryIngredients

Параметр | Описание
-------- | --------
category_name | Название категории ингредиентов

### Параметры ответа menu.createCategoryIngredients

Параметр | Описание
-------- | --------
response | Id созданной категории ингредиентов
