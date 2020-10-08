## menu.getIngredients: List of Ingredients

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.getIngredients'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Response example:

```json
{  
  "response":[  
    {  
      "ingredient_id":"91",
      "ingredient_name":"Jack Daniels",
      "ingredient_barcode": "",
      "category_id":"3",
      "ingredient_left":"443.45000",
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
      "partial_write_off":"0"
    },
    {  
      "ingredient_id":"73",
      "ingredient_name":"Авокадо",
      "ingredient_barcode": "",
      "category_id":"0",
      "ingredient_left":"22.00000",
      "limit_value":"0",
      "time_notif":"0",
      "ingredient_unit":"kg",
      "ingredient_weight":0,
      "ingredients_losses_clear":"11",
      "ingredients_losses_cook":"0",
      "ingredients_losses_fry":"0",
      "ingredients_losses_stew":"0",
      "ingredients_losses_bake":"0",
      "ingredients_type":"1",
      "partial_write_off":"0"
    },
    {  
      "ingredient_id":"74",
      "ingredient_name":"Айсберг с-т",
      "ingredient_barcode": "",
      "category_id":"0",
      "ingredient_left":"379.09000",
      "limit_value":"0",
      "time_notif":"0",
      "ingredient_unit":"kg",
      "ingredient_weight":0,
      "ingredients_losses_clear":"10",
      "ingredients_losses_cook":"0",
      "ingredients_losses_fry":"0",
      "ingredients_losses_stew":"0",
      "ingredients_losses_bake":"0",
      "ingredients_type":"1",
      "partial_write_off":"0"
    }
  ]
}
```

The method returns a list of ingredients

### HTTP request

`GET https://joinposter.com/api/menu.getIngredients`

### GET parameters of the menu.getIngredients request

Parameter | Description
--------- | -----------
id_1c | An optional parameter; if the value is `true`, it returns the product category ID in the 1C system in the response. By default, it is not transmitted.

### The menu.getIngredients response parameters

Parameter | Description
--------- | -----------
response | An array of objects

Inside the `response` parameter, there is an array, each element of which contains the following parameters:

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

