## menu.getProduct: Product or Dish Properties

> Request example which receives product properties:

```php
<?php
$url = 'https://joinposter.com/api/menu.getProduct'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&product_id=142';

$data = sendRequest($url);
```

> Response example:

```json
{  
  "response":{  
    "barcode":"",
    "category_name":"Свежевыжатые соки",
    "unit":"",
    "cost":"1880",
    "cost_netto":"1567",
    "fiscal":"0",
    "hidden":"0",
    "menu_category_id":"16",
    "workshop":"4",
    "nodiscount":"0",
    "photo":"/upload/4/menu/product_1403094607_140.jpg",
    "product_code":"",
    "product_id":"140",
    "product_name":"Апельсиновый",
    "sort_order":"1",
    "tax_id":"0",
    "product_tax_id":"0",
    "type":"3",
    "weight_flag":"0",
    "color":"white",
    "spots":[  
      {  
        "spot_id":"1",
        "price":"40000",
        "profit":"38120",
        "profit_netto":"31767",
        "visible":"1"
      },
      {  
        "spot_id":"2",
        "price":"40000",
        "profit":"38120",
        "profit_netto":"31767",
        "visible":"1"
      }
    ],
    "ingredient_id":"10",
    "cooking_time": "0",
    "out":"0"
  }
}
```

> Request example receives dish properties:

```php
<?php
$url = 'https://joinposter.com/api/menu.getProduct'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&product_id=175';

$data = sendRequest($url);
```

> Response example:

```json
{  
  "response":{  
    "barcode":"123456",
    "category_name":"Коктейли",
    "unit":"kg",
    "cost":"444",
    "cost_netto":"370",
    "fiscal":"0",
    "menu_category_id":"39",
    "workshop":"1",
    "nodiscount":"0",
    "photo":"/upload/pos_cdb_4/menu/product_1439375876_175.jpg",
    "product_code":"",
    "product_id":"175",
    "product_name":"Manhattan Jack",
    "sort_order":"999",
    "tax_id":"0",
    "product_tax_id":"0",
    "type":"2",
    "weight_flag":"0",
    "color":"white",
    "spots":[  
      {  
        "spot_id":"1",
        "price":"60000",
        "profit":"59556",
        "profit_netto":"49630",
        "visible":"1"
      },
      {  
        "spot_id":"2",
        "price":"60000",
        "profit":"59556",
        "profit_netto":"49630",
        "visible":"1"
      }
    ],
    "ingredient_id":"0",
    "out":97,
    "product_production_description":"",
    "ingredients":[  
      {  
        "structure_id":"52",
        "ingredient_id":"92",
        "pr_in_clear":"0",
        "pr_in_cook":"0",
        "pr_in_fry":"0",
        "pr_in_stew":"0",
        "pr_in_bake":"0",
        "structure_unit":"l",
        "structure_type":"1",
        "structure_brutto":30,
        "structure_netto":30,
        "structure_lock":"1",
        "structure_selfprice":"102",
        "structure_selfprice_netto":"85",
        "ingredient_name":"Красный вермут",
        "ingredient_unit":"l",
        "ingredient_weight":"0",
        "ingredients_losses_clear":"0",
        "ingredients_losses_cook":"0",
        "ingredients_losses_fry":"0",
        "ingredients_losses_stew":"0",
        "ingredients_losses_bake":"0"
      },
      {  
        "structure_id":"53",
        "ingredient_id":"91",
        "pr_in_clear":"0",
        "pr_in_cook":"0",
        "pr_in_fry":"0",
        "pr_in_stew":"0",
        "pr_in_bake":"0",
        "structure_unit":"l",
        "structure_type":"1",
        "structure_brutto":60,
        "structure_netto":60,
        "structure_lock":"1",
        "structure_selfprice":"313",
        "structure_selfprice_netto":"261",
        "ingredient_name":"Jack Daniels",
        "ingredient_unit":"l",
        "ingredient_weight":"0",
        "ingredients_losses_clear":"0",
        "ingredients_losses_cook":"0",
        "ingredients_losses_fry":"0",
        "ingredients_losses_stew":"0",
        "ingredients_losses_bake":"0"
      }
    ]
  }
}
```

The method returns the product or dish properties

### HTTP request

`GET https://joinposter.com/api/menu.getProduct`

### GET parameters of the menu.getProduct request

Parameter | Description
--------- | -----------
product_id | Product or dish ID

### The menu.getProduct response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
barcode | Product barcode
category_name | The product category name ID
unit | Product unit
cost | Product food cost in kopecks
cost_netto | Product food cost without VAT in kopecks. Is returned if the 'Calculate cost and net profit' setting is enabled
fiscal | Product fiscal status: 0—non-fiscal, 1—fiscal
menu_category_id | Product category ID
workshop | Product station ID
nodiscount | The status of discounts applied to this product: 0—cannot be applied, 1—can be applied
photo | Product photo
product_code | Storage accounting unit
product_id | Product ID
product_name | Product name
sort_order | Product sort order
tax_id | Product tax ID
product_tax_id | The status of the product tax having been derived from the category tax: 0—not derived, 1—derived
type | Product type: 1—semi-finished, 2—dish, 3—product
weight_flag | The status of a product being sold by weight: 0—not sold by weight, 1—sold by weight
color | The product card color on the register
spots | Locations the product is available at
ingredient_id | Ingredient ID (returned if it’s the product)
cooking_time | Dish cooking time in seconds   
product_production_description | Cooking process description
ingredients | List of ingredients (returned if it’s a dish)

Inside the `spots` parameter, there is an array, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
spot_id | Location ID
price | The location’s product cost in kopecks
profit | The location’s product net profit in kopecks
profit_netto | The location’s product net profit without VAT in kopecks. Is returned if the 'Calculate cost and net profit' setting is enabled
visible | The status of the product being visible at the location: 0 — not visible, 1 — visible

Inside the `group_modifications` parameter, there is an array, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
dish_modification_group_id | Modifiers set ID
name | Modifiers set name
num_min | The minimum number of dish modifications that can be selected in an order from a set
num_max | The maximum number of dish modifications that can be selected in an order from a set
is_deleted | Is the set of dish modifications deleted. 0 - no, 1 - yes
modifications | Array of modifications in a set

Inside the `modifications` parameter, which is contained in `group_modifications`, there is an array, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
dish_modification_id | Modification ID
name | Dish modification name
ingredient_id | Ingredient ID (returned if it’s the product or ingredient)
type | Type of dish modification: 1 - product, 2 - dish, 3 - prepack, 8 - product modification, 10 - ingredient, 0 - No extra ingredients
brutto | Brutto of dish modification
price | Price of dish modification in money
photo_orig | Original photo of dish modification
photo_large | Large photo of dish modification
photo_small | Small photo of dish modification
last_modified_time | Last modified time of dish modification

Inside the `ingredients` parameter, there is an array, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
structure_id | Dish element ID
ingredient_id | Ingredient ID
pr_in_clear | The status of the cleaning method being used: 0—not used, 1—used
pr_in_cook | The status of the baking method being used: 0—not used, 1—used
pr_in_fry | The status of the frying method being used: 0—not used, 1—used
pr_in_stew | The status of the stewing method being used: 0—not used, 1—used
pr_in_bake | The status of the cooking method being used: 0—not used, 1—used
structure_unit | Dish element unit
structure_type | Dish element type: 1—ingredient, 2—semi-finished product
structure_brutto | Dish element gross
structure_netto | Dish element net
structure_lock | Dependence of net from gross: 0—manual, 1—automatic
structure_selfprice | Dish element cost
structure_selfprice_netto | Dish element cost without VAT. Is returned if the 'Calculate cost and net profit' setting is enabled
ingredient_name | Ingredient name
ingredient_unit | Ingredient unit
ingredient_weight | Ingredient waste count
ingredients_losses_clear | Loss rate at the ingredient cleaning
ingredients_losses_cook | Loss rate at the ingredient baking
ingredients_losses_fry | Loss rate at the ingredient frying
ingredients_losses_stew | Loss rate at the ingredient stewing
ingredients_losses_bake | Loss rate at the ingredient cooking
