## menu.removeCategoryIngredients: Удаление категории ингредиентов

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.removeCategoryIngredients'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$category_ingredients = [
    'category_id'      => 2,
    'with_ingredients' => 1,
];

$data = sendRequest($url, 'post', $category_ingredients);
```

> Пример ответа:

```json
{  
  "success":"successful delete category"
}
```

Метод удаляет категорию ингредиентов

### HTTP запрос

`GET https://joinposter.com/api/menu.removeCategoryIngredients`

### POST-параметры запроса menu.removeCategoryIngredients

Параметр | Описание
-------- | --------
category_id | Id категории ингредиентов
with_ingredients | Признак, удалять ли ингредиенты в категории: 0 — не удалять, 1 — удалять. По умолчанию принимает 0.

### Параметры ответа menu.removeCategoryIngredients

Параметр | Описание
-------- | --------
success | Сообщение об успешном удалении
