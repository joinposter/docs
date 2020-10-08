## menu.getIngredient: Ingredient Properties

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.getIngredient'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&ingredient_id=91'
 . '&1c=true';

$data = sendRequest($url);
```

> Response example:

```json
{  
  "response":{  
    "ingredient_id":"91",
    "ingredient_name":"Jack Daniels",
    "ingredient_barcode": "",
    "category_id":"3",
    "ingredient_left":"442.85000",
    "limit_value":"0",
    "time_notif":"0",
    "ingredient_unit":"l",
    "ingredient_weight":0,
    "ingredients_losses_clear":"0",
    "ingredients_losses_cook":"0",
    "ingredients_losses_fry":"0",
    "ingredients_losses_stew":"0",
    "ingredients_losses_bake":"0",
    "ingredients_type":"1",
    "partial_write_off":"0",
    "id_1c":"d70b49a7-0097-11e6-9c83-028037ec0200",
    "delete":"0",
    "hidden":"0"
  }
}
```

The method returns the ingredient properties

### HTTP request

`GET https://joinposter.com/api/menu.getIngredient`

### GET parameters of the menu.getIngredient request

Parameter | Description
--------- | -----------
ingredient_id | Ingredient ID
1c | An optional parameter; if the value is `true`, it returns the product category ID in the 1C system in the response. By default, it is not transmitted.

### The menu.getIngredient response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
ingredient_id | Ingredient ID
ingredient_name | Ingredient name
category_id | The ID of a category the ingredient is in
ingredient_left | Ingredient inventory
limit_value | Ingredient low stock alert threshold in storage
time_notif | The time of the latest notification of the ingredient low stock alert threshold in storage
ingredient_unit | Ingredient unit: kg—kilograms, p—pieces, l—liters
ingredient_weight | Ingredient weight if the ingredient is sold by the piece
ingredients_losses_clear | Loss rate at the ingredient cleaning if the ingredient is not sold by the piece
ingredients_losses_cook | Loss rate at the ingredient baking if the ingredient is not sold by the piece
ingredients_losses_fry | Loss rate at the ingredient frying if the ingredient is not sold by the piece
ingredients_losses_stew | Loss rate at the ingredient stewing if the ingredient is not sold by the piece
ingredients_losses_bake | Loss rate at the ingredient cooking if the ingredient is not sold by the piece
ingredients_type | Type of ingredient: 1—ingredient, 2—systemic ingredient
partial_write_off | The status of an ingredient sold by the piece being allowed to be wasted as the one sold by fractions: 0—not allowed, 1—allowed
id_1c | Ingredient ID in the 1C system
delete | The status of an ingredient having been removed: 0—not removed, 1—removed
hidden | The status of an ingredient being hidden: 0—not hidden, 1—hidden

