## menu.set1cIngredientId: Update the Product ID in the 1C System

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.set1cIngredientId'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$ingredient = [
    'id' => [
        [
            'ingredient_id' => 48,
            'id_1c'         => 'b80ffc81-0fc9-11e7-9ab4-ace01035e460',
        ],
    ],
];

$data = sendRequest($url, 'post', $ingredient);
```

> Response example:

```json
{  
  "success":1
}
```

The method updates the ingredient ID in the 1C system

### HTTP request

`GET https://joinposter.com/api/menu.set1cIngredientId`

### POST parameters of the menu.set1cIngredientId request

Parameter | Description
--------- | -----------
id | An array of objects

Each object, in turn, must contain the following properties:

Parameter | Description
--------- | -----------
ingredient_id | Ingredient ID
id_1c | Ingredient ID in the 1C system

### The menu.set1cIngredientId response parameters

Parameter | Description
--------- | -----------
success | 1 if the ingredient ID in the 1C system has been successfully updated

