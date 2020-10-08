## menu.createIngredient: Create an Ingredient

> Request example:

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

> Request example:

```json
{
  "ingredient_name": "Клубника",
  "category_id": 4,
  "type": "p",
  "weight_ingredient": 200
}
```

> Response example:

```json
{  
  "response":811
}
```

The method creates an ingredient

### HTTP request

`GET https://joinposter.com/api/menu.createIngredient`

### POST parameters of the menu.createIngredient request

Parameter | Description
--------- | -----------
ingredient_name | Ingredient name
category_id | Ingredient category ID
type | Ingredient unit: kg—kilograms, p—pieces, l—liters
ingredient_barcode | Ingredient barcode
weight_ingredient | Ingredient weight if the ingredient is sold by the piece
loss_clear | Loss rate at the ingredient cleaning if the ingredient is not sold by the piece
loss_cook | Loss rate at the ingredient baking if the ingredient is not sold by the piece
loss_fry | Loss rate at the ingredient frying if the ingredient is not sold by the piece
loss_stew | Loss rate at the ingredient stewing if the ingredient is not sold by the piece
loss_bake | Loss rate at the ingredient cooking if the ingredient is not sold by the piece
partial_write_off | The status of an ingredient sold by the piece being allowed to be wasted as the one sold by fractions: 0—not allowed, 1—allowed

### The menu.createIngredient response parameters

Parameter | Description
--------- | -----------
response | The created ingredient ID

