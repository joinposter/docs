## menu.recoverDish: Recover a Dish

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.recoverDish'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$product = [
    'product_id' => 48,
    'menu_category_id' => 10,
    'workshop' => 3,
    'tax_id' => 1,
];

$data = sendRequest($url, 'post', $product);
```

> cURL example:

```php
curl -X POST \
  'http://poster.pos/api/menu.recoverDish?token=687409:4164553abf6a031302898da7800b59fb' \
  -H 'cache-control: no-cache' \
  -H 'content-type: multipart/form-data \
  -F product_id=38 \
  -F menu_category_id=5 \
  -F workshop=4 \
  -F tax_id=2

```

> Response example:

```json
{  
  "response":true
}
```

The method recovers a dish

### POST parameters of the menu.recoverDish request

Parameter | Description
--------- | -----------
product_id | Dish ID, required
menu_category | menu category ID, required
workshop | Workshop ID
tax_id | Tax ID

### The menu.recoverDish response parameters

Parameter | Description
--------- | -----------
response | true if the dish has been successfully recovered

