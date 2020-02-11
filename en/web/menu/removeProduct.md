## menu.removeProduct: Remove a Product

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.removeProduct'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$product = [
    'product_id' => 48,
];

$data = sendRequest($url, 'post', $product);
```

> Response example:

```json
{  
  "response":true
}
```

The method removes a product

### HTTP request

`GET https://joinposter.com/api/menu.removeProduct`

### POST parameters of the menu.removeProduct request

Parameter | Description
--------- | -----------
product_id | Product ID

### The menu.removeProduct response parameters

Parameter | Description
--------- | -----------
response | true if the product has been successfully removed

