## menu.updateIngredient: Update Ingredient Properties

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.updateIngredient'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$ingredient = [
    'id'                => 811,
    'ingredient_name'   => 'Лимон',
    'category_id'       => 4,
    'type'              => 'p',
    'weight_ingredient' => 150,
];

$data = sendRequest($url, 'post', $ingredient);
```

> Response example:

```json
{  
  "response": 811
}
```

The method updates the ingredient properties

### HTTP request

`GET https://joinposter.com/api/menu.updateIngredient`

### POST parameters of the menu.updateIngredient request

Parameter | Description
--------- | -----------
id | Ingredient ID
ingredient_name | Ingredient name
category_id | Ingredient category ID
type | Ingredient unit: kg—kilograms, p—pieces, l—liters You can not change the ingredient unit if it has already been supplied in storage.
weight_ingredient | Ingredient weight if the ingredient is sold by the piece
loss_clear | Loss rate at the ingredient cleaning if the ingredient is not sold by the piece
loss_cook | Loss rate at the ingredient baking if the ingredient is not sold by the piece
loss_fry | Loss rate at the ingredient frying if the ingredient is not sold by the piece
loss_stew | Loss rate at the ingredient stewing if the ingredient is not sold by the piece
loss_bake | Loss rate at the ingredient cooking if the ingredient is not sold by the piece
partial_write_off | The status of an ingredient sold by the piece being allowed to be wasted as the one sold by fractions: 0—not allowed, 1—allowed

### The menu.updateIngredient response parameters

Parameter | Description
--------- | -----------
response | The updated ingredient ID

