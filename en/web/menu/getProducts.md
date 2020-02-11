## menu.getProducts: List of Products and Dishes

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.getProducts'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&category_id=15'
 . '&type=products';

$data = sendRequest($url);
```

> Response example:

```json
{
   "response":[
      {
         "barcode":"4820098749621",
         "category_name":"Вода",
         "unit":"",
         "cost":"100",
         "cost_netto":"83",
         "fiscal":"0",
         "menu_category_id":"15",
         "workshop":"1",
         "nodiscount":"0",
         "photo":"/upload/4/menu/product_1403094564_139.jpg",
         "photo_origin":"/upload/4/menu/product_1403094564_139_original.jpg",
         "product_code":"",
         "product_id":"139",
         "product_name":"Borjomi",
         "sort_order":"999",
         "tax_id":"0",
         "product_tax_id":"2",
         "type":"3",
         "weight_flag":"0",
         "color":"white",
         "ingredient_id":"9",
         "modifications":[
            {
               "modificator_id":"147",
               "modificator_name":"Сок яблочный для кальяна ",
               "modificator_selfprice":"0",
               "modificator_selfprice_netto":"0",
               "order":"0",
               "modificator_barcode":"",
               "modificator_product_code":"",
               "spots":[
                  {
                     "spot_id":"1",
                     "price":"68100",
                     "profit":"68100",
                     "profit_netto":"56750",
                     "visible":"1"
                  },
                  {
                     "spot_id":"2",
                     "price":"68100",
                     "profit":"68100",
                     "profit_netto":"56750",
                     "visible":"1"
                  },
                  {
                     "spot_id":"1",
                     "price":"68100",
                     "profit":"68100",
                     "profit_netto":"56750",
                     "visible":"1"
                  },
                  {
                     "spot_id":"2",
                     "price":"68100",
                     "profit":"68100",
                     "profit_netto":"56750",
                     "visible":"1"
                  }
               ],
               "ingredient_id":"0"
            }
         ],
         "out":0
      },
      {
         "barcode":"",
         "category_name":"Вода",
         "unit":"",
         "cost":"654",
         "cost_netto":"545",
         "fiscal":"0",
         "menu_category_id":"15",
         "workshop":"3",
         "nodiscount":"0",
         "photo":"/upload/4/menu/product_1403094497_138.jpg",
         "photo_origin":"/upload/4/menu/product_1403094497_138_original.jpg",
         "product_code":"",
         "product_id":"138",
         "product_name":"Evian",
         "sort_order":"999",
         "tax_id":"0",
         "product_tax_id":"0",
         "type":"3",
         "weight_flag":"0",
         "color":"white",
         "spots":[
            {
               "spot_id":"1",
               "price":"19000",
               "profit":"18346",
               "profit_netto":"15288",
               "visible":"1"
            },
            {
               "spot_id":"2",
               "price":"19000",
               "profit":"18346",
               "profit_netto":"15288",
               "visible":"1"
            }
         ],
         "ingredient_id":"8",
         "cooking_time": "0",
         "out":0
      }
   ]
}
```

The method returns a list of products and dishes

### HTTP request

`GET https://joinposter.com/api/menu.getProducts`

### GET parameters of the menu.getProducts request

Parameter | Description
--------- | -----------
category_id | Product category ID By default, it is not transmitted.
type | Type: products—products, batchtickets—dishes. By default, it is not transmitted.

### The menu.getProducts response parameters

Parameter | Description
--------- | -----------
response | An array of objects

Inside the `response` parameter, there is an array, each element of which contains the following parameters:

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
photo_origin | Product photo original
product_code | Storage accounting unit, for example, SKU
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
ingredient_unit | Ingredient unit: l—liters, kg—kilograms, p—pieces
ingredient_weight | Ingredient waste count
ingredients_losses_clear | Loss rate at the ingredient cleaning
ingredients_losses_cook | Loss rate at the ingredient baking
ingredients_losses_fry | Loss rate at the ingredient frying
ingredients_losses_stew | Loss rate at the ingredient stewing
ingredients_losses_bake | Loss rate at the ingredient cooking
