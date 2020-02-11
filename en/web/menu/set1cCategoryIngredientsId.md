## menu.set1cCategoryIngredientsId: Update the Ingredient Category ID in the 1C System

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.set1cCategoryIngredientsId'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$category_ingredients = [
    'id' => [
        [
            'category_id' => 3,
            'id_1c'       => 'b80ffc81-0fc9-11e7-9ab4-ace01035e460',
        ],
    ],
];

$data = sendRequest($url, 'post', $category_ingredients);
```

> Response example:

```json
{  
  "success":1
}
```

The method updates the ingredient category ID in the 1C system

### HTTP request

`GET https://joinposter.com/api/menu.set1cCategoryIngredientsId`

### POST parameters of the menu.set1cCategoryIngredientsId request

Parameter | Description
--------- | -----------
id | An array of objects

Each object, in turn, must contain the following properties:

Parameter | Description
--------- | -----------
category_id | Ingredient category ID
id_1c | Ingredient category ID in the 1C system

### The menu.set1cCategoryIngredientsId response parameters

Parameter | Description
--------- | -----------
success | 1 if the ingredient category ID in the 1C system has been successfully updated

