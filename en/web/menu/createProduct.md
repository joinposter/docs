## menu.createProduct: Create a Product

> Request example which creates product without modifications:

```php
<?php
$url = 'https://joinposter.com/api/menu.createProduct'
  . '?token=687409:4164553abf6a031302898da7800b59fb';

$product = [
    'product_name'           => 'Пончик',
    'menu_category_id'       => 0,
    'workshop'               => 1,
    'weight_flag'            => 0,
    'color'                  => 'red',
    'different_spots_prices' => 0,
    'modifications'          => 0,
    'barcode'                => '4820098749621',
    'cost'                   => 2000,
    'price'                  => 3000,
    'visible'                => 1,
];

$data = sendRequest($url, 'post', $product);
```

> Response example:

```json
{  
  "response":60
}
```

> Request example which creates product with modifications:


```php
<?php
$url = 'https://joinposter.com/api/menu.createProduct'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$product = [
    'product_name'           => 'Sprite',
    'menu_category_id'       => 0,
    'workshop'               => 1,
    'weight_flag'            => 0,
    'color'                  => 'red',
    'different_spots_prices' => 0,
    'modifications'          => 1,
    'modificator_name[0]'    => '1 л.',
    'modificator_name[1]'    => '2 л.',
    'barcode[0]'             => '4820098749621',
    'barcode[1]'             => '4820098749622',
    'product_code[0]'        => '3412356',
    'product_code[1]'        => '3412357',
    'cost[0]'                => 700,
    'cost[1]'                => 1000,
    'price[0]'               => 1500,
    'price[1]'               => 2000,
    'visible[0]'             => 1,
    'visible[1]'             => 1,
];

$data = sendRequest($url, 'post', $product);
```

> Response example:

```json
{  
  "response":61,
  "modifications_id":[  
    1,
    2
  ]
}
```

The method creates a product

### HTTP request

`POST https://joinposter.com/api/menu.createProduct`

### POST parameters of the menu.createProduct request

Parameter | Description
--------- | -----------
product_name | Product name
menu_category_id | Products category ID If you transmit 0, the product will go to the Home Screen.
workshop | Station ID. A mandatory property for cafe-type accounts.
weight_flag | The status of the product being sold by the piece or by weight: 0—sold by the piece, 1—sold by weight
color | Product card color: white, red, orange, yellow, green, blue, navy blue, purple, black, mint blue, lime green, pink. The default color is white.
different_spots_prices | The status of the product having different costs at different locations: 0—the same costs, 1—different costs
modifications | The status of the product having modifiers: 0—without modifiers, 1—with modifiers
modificator_name | Modifier name. It is mandatory if 1 is transmitted in the modifications parameter. All names are transmitted with the modifier index in square brackets: modificator_name [0], modificator_name [1], and so on.
barcode | Product barcode. It allows using a barcode scanner during the product sale. For products sold by the piece, it is recommended to use a 13-digit code; for sold-by-weight products, it is recommended to use a 7-digit code. If a product is without modifiers, the parameter is transmitted as a barcode; if it is with modifiers, the modifier index is specified in square brackets: barcode [0], barcode [1], and so on.
product_code | Product SKU. It is specified only for store-type accounts. If a product is without modifiers, the parameter is transmitted as product_code; if it is with modifiers, the modifier index is specified in square brackets: product_code [0], product_code [1], and so on.
cost | The primary product food cost in kopecks, which will be used before the first product supply. If a product is without modifiers, the parameter is transmitted as cost; if it is with modifiers, the modifier index is specified in square brackets: cost [0], cost [1], and so on.
price | Product cost in kopecks If a product is without modifiers, the parameter is transmitted as price; if it is with modifiers, the modifier index is specified in square brackets: price [0], price [1], and so on. In addition, if the Different Costs at Different Locations property is enabled, one more array level is added, where the locations IDs will be specified. That is, price [1], price [2], and so on are without modifiers, while price [0] [1], price [1] [2] are with modifiers (as an index, the modification index comes first, followed by the location ID).
visible | The status of the product being visible on the register at the location: 0—not visible, 1—visible It is used only when the Different Costs at Different Locations property is enabled. The data transmission structure is identical to the price parameter. That is, visible [1], visible [2], and so on are without modifiers (with a location ID as an index), while visible [0] [1], visible [1] [2] are with modifications (as an index, the modification index comes first, followed by the location ID).

### The menu.createProduct response parameters without modifications

Parameter | Description
--------- | -----------
response | Created product ID

### The menu.createProduct response parameters with modifications

Parameter | Description
--------- | -----------
product_id | Created product ID
modifications_id | An array of the created product ID modifications

