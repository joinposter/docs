## menu.updatePrepack: Update the Semi-Finished Product Properties

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.updatePrepack'
    . '?token=687409:4164553abf6a031302898da7800b59fb';

$prepack = [
    'prepack_id' => 919,
    'product_name' => 'Блины',
    'ingredient'   => [
        [
            'id'     => 88,
            'type'   => 1,
            'brutto' => 3,
            'netto'  => 6,
            'lock'   => 0,
            'clear'  => 0,
            'cook'   => 0,
            'fry'    => 0,
            'stew'   => 1,
            'bake'   => 0,
        ],
    ],
];

$data = sendRequest($url, 'post', $prepack);
```

> Response example:

```json
{  
  "response": 919
}
```

The method updates the semi-finished product properties

### HTTP request

`GET https://joinposter.com/api/menu.updatePrepack`

### POST parameters of the menu.updatePrepack request

Parameter | Description
--------- | -----------
prepack_id | Semi-finished product ID
product_name | Semi-finished product name
product_production_description | Cooking process description
ingredient | Ingredients included in the semi-finished product

Inside the `ingredients` parameter, there is an array, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
id | The ID of an ingredient or semi-finished product
type | The semi-finished product element type: 1—ingredient, 2—semi-finished product
brutto | Gross of a semi-finished product element
netto | Net of a semi-finished product element
lock | Dependence of net from gross: 0—manual, 1—automatic
clear | The status of the cleaning method being used: 0—not used, 1—used The default value is 0.
cook | The status of the baking method being used: 0—not used, 1—used. The default value is 0.
fry | The status of the frying method being used: 0—not used, 1—used. The default value is 0.
stew | The status of the stewing method being used: 0—not used, 1—used. The default value is 0.
bake | The status of the cooking method being used: 0—not used, 1—used. The default value is 0.

### The menu.updatePrepack response parameters

Parameter | Description
--------- | -----------
response | The updated semi-finished product ID in the products table

