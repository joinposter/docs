## menu.updateIngredients: Групповое изменение ингредиентов

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.updateIngredients'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$ingredients = [
    [
        'id'              => '7',
        'ingredient_name' => 'Яблоко',
        'type'            => 'p',
    ],
    [
        'id'              => '8',
        'ingredient_name' => 'Груша',
        'type'            => 'p',
    ]
];

$data = sendRequest($url, 'post', $ingredients);
```

> Пример запроса:

```json
[
  {
    "id": 7,
    "ingredient_name": "Яблоко",
    "type": "p"
  },
  {
    "id": 8,
    "ingredient_name": "Груша",
    "type": "p"
  }
]
```

> Пример ответа:

```json
{
  "response": [
    7,
    8
  ]
}
```

Метод изменяет несколько ингредиентов за один запрос

### HTTP запрос

`POST https://joinposter.com/api/menu.updateIngredients`

### POST-параметры запроса menu.updateIngredients

Параметр | Описание
-------- | --------
id | Id ингредиента
ingredient_name | Название ингредиента
category_id | Id категории ингредиента
type | Единица измерения ингредиента: kg — килограммы, p — штуки, l — литры
ingredient_barcode | Штрихкод ингредиента
weight_ingredient | Вес ингредиента, если ингредиент штучный
loss_clear | Коэффициент потерь при очистке ингредиента, если ингредиент не штучный
loss_cook | Коэффициент потерь при запекании ингредиента, если ингредиент не штучный
loss_fry | Коэффициент потерь при жарке ингредиента, если ингредиент не штучный
loss_stew | Коэффициент потерь при тущении ингредиента, если ингредиент не штучный
loss_bake | Коэффициент потерь при варке ингредиента, если ингредиент не штучный
partial_write_off | Признак, что можно списывать штучный ингредиент, как дробный: 0 — нельзя, 1 — можно

### Параметры ответа menu.updateIngredients

Параметр | Описание
-------- | --------
response | Массив id изменённых ингредиентов
