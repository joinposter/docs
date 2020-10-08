## menu.updateProductPrice: Change product price

> Example of a request to change the price of a product:

```php
<?php
$url = 'https://joinposter.com/api/menu.updateProductPrice'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$product = [
    'spot_id'          => 1,
    'price'            => '100',
    'product_id'       => 139,
    'modificator_id'   => 0,
];

$data = sendRequest($url, 'post', $product);
```

> Sample response:

```json
{  
  "success": 1
}
```

The method changes the price of one or more products

### HTTP POST request

`POST https://joinposter.com/api/menu.updateProductPrice`

### POST request parameters menu.updateProductPrice

Parameter | Description
-------- | --------
spot_id | ID of the spot, required parameter when product_id is passed
price | An optional parameter, price in cents
product_id | ID of the product
modificator_id | An optional parameter, ID of the product modification
products | An optional array products
modifications | An optional array of modifications

### POST parameters of the products array

Parameter | Description
-------- | --------
id | Id product
spot_id | ID of the spot
price | Price in cents

### POST parameters of the modifications array

Parameter | Description
-------- | --------
id | ID of product/dish modification
spot_id | ID of the spot, required parameter for product modification
price | Price in cents


### menu.updateProductPrice response parameters

Parameter | Description
-------- | --------
success | 1 — in case of successful operation

