## menu.createPrepack: Create a Semi-Finished Product

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.createPrepack'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$prepack = [
    'product_name' => 'Маринованные грибы',
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
  "response":177
}
```

The method creates a semi-finished product

### HTTP request

`GET https://joinposter.com/api/menu.createPrepack`

### POST parameters of the menu.createDish request

Parameter | Description
--------- | -----------
product_name | Semi-finished product name. It has to be unique.
ingredient | Ingredients included in the semi-finished product
product_production_description | An optional parameter, the description of the cooking process.

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

### The menu.createPrepac response parameters

Parameter | Description
--------- | -----------
response | The created semi-finished product ID in the products table

