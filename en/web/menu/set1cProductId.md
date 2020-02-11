## menu.set1cProductId: Update the Product ID in the 1C System

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.set1cProductId'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$products = [
    'id' => [
        [
            'product_id' => 48,
            'id_1c'      => 'b80ffc81-0fc9-11e7-9ab4-ace01035e460',
        ],
    ],
];

$data = sendRequest($url, 'post', $products);
```

> Response example:

```json
{  
  "success":1
}
```

The method updates the product ID in the 1C system

### HTTP request

`GET https://joinposter.com/api/menu.set1cProductId`

### POST parameters of the menu.set1cProductId request

Parameter | Description
--------- | -----------
id | An array of objects

Each object, in turn, must contain the following properties:

Parameter | Description
--------- | -----------
product_id | Product ID
id_1c | Product ID in the 1C system

### The menu.set1cProductId response parameters

Parameter | Description
--------- | -----------
success | 1 if the product ID in the 1C system is successfully updated

