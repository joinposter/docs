## menu.updateProduct: Update the Product Properties

> Request example to change the product data without modifications and with different prices in different spots:

```php
<?php
$url = 'https://joinposter.com/api/menu.updateProduct'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$product = [
    'id'                     => 142,
    'product_name'           => 'Батон',
    'menu_category_id'       => 0,
    'workshop'               => 1,
    'weight_flag'            => 0,
    'color'                  => 'blue',
    'different_spots_prices' => 1,
    'modifications'          => 0,
    'barcode'                => '4820098749621',
    'price[1]'               => 3100,
    'price[2]'               => 3200,
    'visible'                => 1,
];

$data = sendRequest($url, 'post', $product);
```

> Response example:

```json
{  
  "response": 142
}
```

> Request example to change product without modifications:

```php
<?php
$url = 'https://joinposter.com/api/menu.updateProduct'
    . '?token=687409:4164553abf6a031302898da7800b59fb';

$product = [
    'id'                     => 57,
    'product_name'           => 'Имбирный чай',
    'menu_category_id'       => 0,
    'workshop'               => 1,
    'weight_flag'            => 0,
    'color'                  => 'green',
    'different_spots_prices' => 1,
    'modifications'          => 1,
    'modificator_id[0]'      => 1,
    'modificator_id[1]'      => 0,
    'modificator_id[2]'      => 2,
    'modificator_name[0]'    => '1л',
    'modificator_name[1]'    => '1.5л',
    'modificator_name[2]'    => '2л',
    'barcode[0]'             => '4820098749621',
    'barcode[1]'             => '4820098749623',
    'barcode[2]'             => '4820098749622',
    'price[0][1]'            => 1500,
    'price[0][2]'            => 1600,
    'price[1][1]'            => 1700,
    'price[1][2]'            => 1800,
    'price[2][1]'            => 2000,
    'price[2][2]'            => 2100,
    'visible[0][1]'          => 1,
    'visible[0][2]'          => 1,
    'visible[1][1]'          => 1,
    'visible[1][2]'          => 1,
    'visible[2][1]'          => 0,
    'visible[2][2]'          => 0,
];

$data = sendRequest($url, 'post', $product);
```

> Response example:

```json
{  
  "response":{  
    "product_id":61,
    "modifications_id":[  
      1,
      7,
      2
    ]
  }
}
```

The method updates the product properties

### HTTP request

`POST https://joinposter.com/api/menu.updateProduct`

### POST parameters of the menu.updateProduct request

Parameter | Description
--------- | -----------
id | Product ID
product_name | Product name
menu_category_id | Products category ID If you transmit 0, the product will go to the Home Screen.
workshop | Station ID. A mandatory property for cafe-type accounts.
weight_flag | The status of the product being sold by the piece or by weight: 0—sold by the piece, 1—sold by weight
color | Product card color: white, red, orange, yellow, green, blue, navy blue, purple, black, mint blue, lime green, pink. The default color is white.
different_spots_prices | The status of the product having different costs at different locations: 0—the same costs, 1—different costs
modifications | The status of the product having modifiers: 0—without modifiers, 1—with modifiers
modificator_id | Modifier ID. It is mandatory if 1 is transmitted in the modifications parameter. For existing modifiers, you need to transmit their existing modificator_id. For new modifiers, you must transmit 0.
modificator_name | Modifier name. It is mandatory if 1 is transmitted in the modifications parameter. All names are transmitted with the modifier index in square brackets: modificator_name [0], modificator_name [1], and so on.
barcode | Product barcode. It allows using a barcode scanner during the product sale. For products sold by the piece, it is recommended to use a 13-digit code; for sold-by-weight products, it is recommended to use a 7-digit code. If a product is without modifiers, the parameter is transmitted as a barcode; if it is with modifiers, the modifier index is specified in square brackets: barcode [0], barcode [1], and so on.
product_code | Product SKU. It is specified only for store-type accounts. If a product is without modifiers, the parameter is transmitted as product_code; if it is with modifiers, the modifier index is specified in square brackets: product_code [0], product_code [1], and so on.
price | Product cost in kopecks If a product is without modifiers, the parameter is transmitted as price; if it is with modifiers, the modifier index is specified in square brackets: price [0], price [1], and so on. In addition, if the Different Costs at Different Locations property is enabled, one more array level is added, where the locations IDs will be specified. That is, price [1], price [2], and so on are without modifiers, while price [0] [1], price [1] [2] are with modifiers (as an index, the modification index comes first, followed by the location ID).
visible | The status of the product being visible on the register at the location: 0—not visible, 1—visible It is used only when the Different Costs at Different Locations property is enabled. The data transmission structure is identical to the price parameter. That is, visible [1], visible [2], and so on are without modifiers (with a location ID as an index), while visible [0] [1], visible [1] [2] are with modifications (as an index, the modification index comes first, followed by the location ID).

### The menu.updateProduct response parameters without modifications

Parameter | Description
--------- | -----------
response | Updated product ID

### The menu.updateProduct response parameters with modifications

Parameter | Description
--------- | -----------
product_id | Updated product ID
modifications_id | An array of the updated product ID modifications

