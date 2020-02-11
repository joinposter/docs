## menu.createDish: Create a Dish

> Request example which creates dish:

```php
<?php
$url = 'https://joinposter.com/api/menu.createDish'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$dish = [
    'product_name' => 'Кальян с сюрпризом',
    'menu_category_id' => 151,
    'different_spots_prices' => 1,
    'workshop' => 4,
    'weight_flag' => 0,
    'product_color' => 'red',
    'nodiscount' => 1,
    'price' => [
        1 => 55,
        2 => 57,
    ],
    'visible' => [
        1 => 1,
        2 => 0,
    ],
    "ingredient" => [[
        "id" => 813,
        "type" => 1,
        "unit" => "kg",
        "weight" => 0,
        "stew" => 0,
        "bake" => 0,
        "brutto" => 10,
        "lock" => 1,
        "netto" => 10,
    ]],
    'modificationgroup' => [
        [
            'type'          => 1,
            'minNum'        => 1,
            'maxNum'        => 1,
            'name'          => 'Чаша',
            "modifications" => [
                [
                    "ingredientId" => 820,
                    "type" => 1,
                    "name" => "Классическая чаша",
                    "brutto" => 1,
                    "price" => 500,
                ],
                [
                    "ingredientId" => 816,
                    "name" => "Апельсиновая чаша",
                    "type" => 1,
                    "brutto" => 1,
                    "price" => 400,
                ],
            ]
        ]
    ]
];

$data = sendRequest($url, 'post', $dish);
```

> Response example:

```json
{
  "response":61
}
```

The method creates a dish

!>     You cannot create a dish with modifications if it is:
- sold by weight, wait_flag—1
- participates in promotions or is in a category that participates in the promotion
- is an element of a dish with a modification — participates in waste or manufacture

### HTTP request

`POST https://joinposter.com/api/menu.createDish`

### POST parameters of the menu.createDish request

Parameter | Description
--------- | -----------
product_name | Dish name
barcode | Dish barcode. By default, it is not transmitted.
menu_category_id | The ID of the dish category. The default value is 0.
workshop_id | Station ID. The default value is 1.
product_color | Dish card color: white, red, orange, yellow, green, blue, navy blue, purple, black, mint blue, lime green, pink. The default color is white.
weight_flag | The status of a dish being sold by weight: 0—not sold by weight, 1—sold by weight. The default value is 0. If a dish has an ingredient sold by the piece, it can not be sold by weight. If a dish is with modifications, it cannot be sold by weight.
nodiscount | The status of the dish participating in discounts: 0—does not participate, 1—participates. The default value is 1.
price | An array of prices for different locations. The array key is the location ID; the value is the price in kopecks. You can specify price not as an array; the price then is distributed among all locations.
visible | The viewability array of a dish for different locations. The array key is a location ID. You can specify visible not as an array, the viewability then is distributed among all locations.
ingredient | An array of ingredients and semi-finished products included in a dish recipe
modificationgroup | An array of modifier groups

Inside the `ingredient` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
id | The ID of a semi-finished product or ingredient
type | Ingredient type: 1—ingredient, 2—semi-finished product
brutto | Gross
netto | Net
bake | The status of the cooking method being used: 0—not used, 1—used. By default, 0 is transmitted.
cook | The status of the baking method being used: 0—not used, 1—used. By default, 0 is transmitted.
clear | The status of the cleaning method being used: 0—not used, 1—used. By default, 0 is transmitted.
fry | The status of the frying method being used: 0—not used, 1—used. By default, 0 is transmitted.
stew | The status of the stewing method being used: 0—not used, 1—used. By default, 0 is transmitted.
lock | The dependence type of net from gross: 0—manual, 1—automatic

Inside the `modificationgroup` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
type | Type: 1—of several, 2—some of several
minNum | The minimum modifiers number to select
maxNum | The maximum modifiers number to select
name | Modifier group name
modifications | An array of modifiers

Inside the `modificationgroup` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
ingredientId | The ID of the ingredient of a dish or semi-finished product
type | Type: 10 - ingredient, 1 - product, 2 - dish, 3 - prepack, 8 - product modification
name | Modifier name
brutto | Modifier weight, quantity, or liters
price | Delta of the price added to the product when adding a modification. The price is in kopecks and can be zero.

### The menu.createDish response parameters

Parameter | Description
--------- | -----------
response | The ID of the created dish

