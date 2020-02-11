## menu.set1cModificatorId: Update the Product Modifier ID in the 1C System

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.set1cModificatorId'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$product_modificators = [
    'id' => [
        [
            'modificator_id' => 7,
            'id_1c'          => 'b80ffc81-0fc9-11e7-9ab4-ace01035e460',
        ],
    ],
];

$data = sendRequest($url, 'post', $product_modificators);
```

> Response example:

```json
{  
  "success":1
}
```

The method updates the product modifier ID in the 1C system

### HTTP request

`GET https://joinposter.com/api/menu.set1cModificatorId`

### POST parameters of the menu.set1cModificatorId request

Parameter | Description
--------- | -----------
id | An array of objects

Each object, in turn, must contain the following properties:

Parameter | Description
--------- | -----------
modificator_id | Product modifier ID
id_1c | Product modifier ID in the 1C system

### The menu.set1cModificatorId response parameters

Parameter | Description
--------- | -----------
success | 1 if the product modifier ID in the 1C system is successfully updated

