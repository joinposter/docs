## menu.set1cCategoryId: Update the Product Category ID in the 1C System

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.set1cCategoryId'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$category = [
    'id' => [
        [
            'category_id' => 32,
            'id_1c'       => 'b80ffc81-0fc9-11e7-9ab4-ace01035e460',
        ],
    ],
];

$data = sendRequest($url, 'post', $category);
```

> Response example:

```json
{  
  "success":1
}
```

The method updates the product category ID in the 1C system

### HTTP request

`GET https://joinposter.com/api/menu.set1cCategoryId`

### POST parameters of the menu.set1cCategoryId request

Parameter | Description
--------- | -----------
id | An array of objects

Each object, in turn, must contain the following properties:

Parameter | Description
--------- | -----------
category_id | Product category ID
id_1c | Product category ID in the 1C system

### The menu.set1cCategoryId response parameters

Parameter | Description
--------- | -----------
success | 1 if the product category ID in the 1C system is successfully updated

