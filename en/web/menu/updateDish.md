## menu.updateDish: Update Dish Properties

> Request example which changes dish:

```php
<?php
$url = 'https://joinposter.com/api/menu.updateDish'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$dish = [
    'dish_id'                => 171,
    'product_name'           => 'Гамбургер с телятиной',
    'barcode'                => 159687,
    'menu_category_id'       => 10,
    'different_spots_prices' => 1,
    'workshop'               => 2,
    'weight_flag'            => 0,
    'product_color'          => 'red',
    'nodiscount'             => 0,
    'ingredient'             => [
        [
            'id'     => 815,
            'type'   => 1,
            'brutto' => 3,
            'netto'  => 6,
            'lock'   => 1,
            'clear'  => 1,
        ]
    ],
    'price' => [
        1 => 55,
        2 => 57,
    ],
    'visible' => [
        1 => 1,
        2 => 0,
    ],
    'modificationgroup'      => [
        [
            'type'          => 1,
            'minNum'        => 1,
            'maxNum'        => 1,
            'name'          => 'Картофель',
            'modifications' => [
                [
                    'ingredientId' => 814,
                    'type'         => 1,
                    'name'         => 'Вареный картофель',
                    'brutto'       => 200,
                    'price'        => 230,
                ],
                [
                    'ingredientId' => 816,
                    'type'         => 1,
                    'name'         => 'Фри',
                    'brutto'       => 150,
                    'price'        => 280,
                ],
            ],
        ]
    ],
];

$data = sendRequest($url, 'post', $dish);
```

> Response example:

```json
{
  "response":61
}
```

The method updates dish properties

!>     You cannot create a dish with modifications if it is:
- sold by weight, weight_flag—1
- participates in promotions or is in a category that participates in the promotion
- is an element of a dish with a modification — participates in waste or manufacture

### HTTP request

`POST https://joinposter.com/api/menu.updateDish`

### POST parameters of the menu.updateDish request

Parameter | Description
--------- | -----------
dish_id | Dish ID
product_name | Dish name
barcode | Dish barcode
menu_category_id | Dish category ID
workshop_id | Station ID
product_color | Dish card color: white, red, orange, yellow, green, blue, navy blue, purple, black, mint blue, lime green, pink
weight_flag | The status of a dish being sold by weight: 0—not sold by weight, 1—sold by weight. If a dish has an ingredient sold by the piece, it can not be sold by weight.
nodiscount | The status of a dish participating in discounts: 0—does not participate, 1—participates
price | An array of prices for different locations. The array key is a location ID. You can specify price not as an array; the price then is distributed among all locations.
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
dish_modification_group_id | The ID of the group being edited. All product modification groups that do not come with the request will be removed.
type | Type: 1—of several, 2—some of several
minNum | The minimum modifiers number to select
maxNum | The maximum modifiers number to select
name | Modifier group name
modifications | An array of modifiers

Inside the `modificationgroup` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
dish_modification_id | The ID of the modification being edited. All product modifications that do not come with the request will be removed.
ingredientId | The ID of the ingredient of a dish or semi-finished product
type | Type: 1—ingredient, 2—dish or semi-finished product
name | Modifier name
brutto | Modifier weight, quantity, or liters
price | Delta of the price added to the product when adding a modification. It can be zero.

### The menu.updateDish response parameters

Parameter | Description
--------- | -----------
response | The ID of the dish updated

