## menu.getPrepacks: List of Semi-Finished Products

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.getPrepacks'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Response example:

```json
{  
  "response":[  
    {  
      "product_id":"167",
      "ingredient_id":"0",
      "product_name":"Куринный бульон",
      "cost":"1222",
      "cost_netto":"1018",
      "out":171,
      "product_production_description":"",
      "ingredients":[  
        {  
          "structure_id":"45",
          "ingredient_id":"88",
          "pr_in_clear":"0",
          "pr_in_cook":"1",
          "pr_in_fry":"0",
          "pr_in_stew":"0",
          "pr_in_bake":"0",
          "structure_unit":"kg",
          "structure_type":"1",
          "structure_brutto":200,
          "structure_netto":170,
          "structure_lock":"1",
          "structure_selfprice":"1221",
          "structure_selfprice_netto":"1018",
          "ingredient_name":"Куриные крылья",
          "ingredient_unit":"kg",
          "ingredient_weight":"0",
          "ingredients_losses_clear":"0",
          "ingredients_losses_cook":"15",
          "ingredients_losses_fry":"16",
          "ingredients_losses_stew":"16",
          "ingredients_losses_bake":"16"
        },
        {  
          "structure_id":"46",
          "ingredient_id":"89",
          "pr_in_clear":"0",
          "pr_in_cook":"0",
          "pr_in_fry":"0",
          "pr_in_stew":"0",
          "pr_in_bake":"0",
          "structure_unit":"kg",
          "structure_type":"1",
          "structure_brutto":1,
          "structure_netto":1,
          "structure_lock":"1",
          "structure_selfprice":"1",
          "structure_selfprice_netto":"1",
          "ingredient_name":"Соль",
          "ingredient_unit":"kg",
          "ingredient_weight":"0",
          "ingredients_losses_clear":"0",
          "ingredients_losses_cook":"0",
          "ingredients_losses_fry":"0",
          "ingredients_losses_stew":"0",
          "ingredients_losses_bake":"0"
        }
      ]
    }
  ]
}
```

The method returns a list of semi-finished products

### HTTP request

`GET https://joinposter.com/api/menu.getPrepacks`

### GET parameters of the menu.getPrepacks request

Parameter | Description
--------- | -----------
1c | An optional parameter; if the value is `true`, it returns the product category ID in the 1C system in the response. By default, it is not transmitted.

### The menu.getPrepacks response parameters

Parameter | Description
--------- | -----------
response | An array of objects

Inside the `response` parameter, there is an array, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
product_id | The semi-finished product ID in the products table
ingredient_id | The semi-finished product ID in the ingredients table if the semi-finished product is manufacturable; otherwise, it takes 0
product_name | Semi-finished product name
cost | Semi-finished product food cost
cost_netto | Semi-finished product food cost without VAT. Is returned if the 'Calculate cost and net profit' setting is enabled
out | Semi-finished product weight
product_production_description | Cooking process description
id_1c | Semi-finished product ID in the 1C system
ingredients | Ingredients included in the semi-finished product

Inside the `ingredients` parameter, there is an object with the following parameter:

Parameter | Description
--------- | -----------
structure_id | Semi-finished product element ID
ingredient_id | Ingredient ID
pr_in_clear | The status of the cleaning method being used: 0—not used, 1—used
pr_in_cook | The status of the baking method being used: 0—not used, 1—used
pr_in_fry | The status of the frying method being used: 0—not used, 1—used
pr_in_stew | The status of the stewing method being used: 0—not used, 1—used
pr_in_bake | The status of the cooking method being used: 0—not used, 1—used
structure_unit | Unit of a semi-finished product element
structure_type | The semi-finished product element type: 1—ingredient, 2—semi-finished product
structure_brutto | Gross of a semi-finished product element
structure_netto | Net of a semi-finished product element
structure_lock | Dependence of net from gross: 0—manual, 1—automatic
structure_selfprice | The price of a semi-finished product element
structure_selfprice_netto | The price of a semi-finished product element without VAT in kopecks. Is returned if the 'Calculate cost and net profit' setting is enabled
ingredient_name | Ingredient name
ingredient_unit | Ingredient unit: kg—kilograms, p—pieces, l—liters
ingredient_weight | Ingredient waste count
ingredients_losses_clear | Loss rate at the ingredient cleaning
ingredients_losses_cook | Loss rate at the ingredient baking
ingredients_losses_fry | Loss rate at the ingredient frying
ingredients_losses_stew | Loss rate at the ingredient stewing
ingredients_losses_bake | Loss rate at the ingredient cooking

