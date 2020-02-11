## menu.updateCategoryIngredients: Изменение свойств категории ингредиентов

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.updateCategoryIngredients'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$category_ingredients = [
    'category_id'   => 2,
    'category_name' => 'Фрукты',
];

$data = sendRequest($url, 'post', $category_ingredients);
```

> Пример ответа:

```json
{  
  "response": 2
}
```

Метод изменяет свойства категории ингредиентов

### HTTP запрос

`GET https://joinposter.com/api/menu.updateCategoryIngredients`

### POST-параметры запроса menu.updateCategoryIngredients

Параметр | Описание
-------- | --------
category_id | Id категории ингредиентов
category_name | Новое название категории ингредиентов

### Параметры ответа menu.updateCategoryIngredients

Параметр | Описание
-------- | --------
response | Id изменённой категории ингредиентов
