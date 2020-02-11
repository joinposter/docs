## menu.removeIngredient: Удаление ингредиета

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.removeIngredient'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$ingredient = [
    'ingredient_id' => 811,
];

$data = sendRequest($url, 'post', $ingredient);
```

> Пример ответа:

```json
{  
  "response":true
}
```

Метод удаляет ингредиет

### HTTP запрос

`GET https://joinposter.com/api/menu.removeIngredient`

### POST-параметры запроса menu.removeIngredient

Параметр | Описание
-------- | --------
ingredient_id | Id ингредиета

### Параметры ответа menu.removeIngredient

Параметр | Описание
-------- | --------
response | true, если ингредиет успешно удалён
