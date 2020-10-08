## menu.updateIngredients: Update list of Ingredients

> Request example:

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

> Request example:

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

> Response example:

```json
{
  "response": [
    7,
    8
  ]
}
```

The method updates a list of ingredients

### HTTP request

`POST https://joinposter.com/api/menu.updateIngredients`

### POST parameters of the menu.updateIngredients

Parameter | Description
-------- | --------
id | Ingredient ID
ingredient_name | Ingredient name
category_id | Ingredient category ID
ingredient_barcode | Ingredient barcode
type | Ingredient unit: kg—kilograms, p—pieces, l—liters You can not change the ingredient unit if it has already been supplied in storage.
weight_ingredient | Ingredient weight if the ingredient is sold by the piece
loss_clear | Loss rate at the ingredient cleaning if the ingredient is not sold by the piece
loss_cook | Loss rate at the ingredient baking if the ingredient is not sold by the piece
loss_fry | Loss rate at the ingredient frying if the ingredient is not sold by the piece
loss_stew | Loss rate at the ingredient stewing if the ingredient is not sold by the piece
loss_bake | Loss rate at the ingredient cooking if the ingredient is not sold by the piece
partial_write_off | The status of an ingredient sold by the piece being allowed to be wasted as the one sold by fractions: 0—not allowed, 1—allowed

### The menu.updateIngredients response parameters

Parameter | Description
-------- | --------
response | Array of id updated ingredients
