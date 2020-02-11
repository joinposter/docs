## menu.createIngredient: Создание ингредиента

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.createIngredient'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$ingredient = [
    'ingredient_name'   => 'Клубника',
    'category_id'       => 4,
    'type'              => 'p',
    'weight_ingredient' => 200,
];

$data = sendRequest($url, 'post', $ingredient);
```

> Пример ответа:

```json
{  
  "response":811
}
```

Метод создаёт ингредиент

### HTTP запрос

`GET https://joinposter.com/api/menu.createIngredient`

### POST-параметры запроса menu.createIngredient

Параметр | Описание
-------- | --------
ingredient_name | Название ингредиента
category_id | Id категории ингредиента
type | Единица измерения ингредиента: kg — килограммы, p — штуки, l — литры
weight_ingredient | Вес ингредиента, если ингредиент штучный
loss_clear | Коэффициент потерь при очистке ингредиента, если ингредиент не штучный
loss_cook | Коэффициент потерь при запекании ингредиента, если ингредиент не штучный
loss_fry | Коэффициент потерь при жарке ингредиента, если ингредиент не штучный
loss_stew | Коэффициент потерь при тущении ингредиента, если ингредиент не штучный
loss_bake | Коэффициент потерь при варке ингредиента, если ингредиент не штучный
partial_write_off | Признак, что можно списывать штучный ингредиент, как дробный: 0 — нельзя, 1 — можно

### Параметры ответа menu.createIngredient

Параметр | Описание
-------- | --------
response | Id созданного ингредиента
