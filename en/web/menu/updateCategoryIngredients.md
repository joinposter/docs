## menu.updateCategoryIngredients: Update the Ingredient Category Properties

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.updateCategoryIngredients'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$category_ingredients = [
    'category_id'   => 2,
    'category_name' => 'Фрукты',
];

$data = sendRequest($url, 'post', $category_ingredients);
```

> Response example:

```json
{  
  "response": 2
}
```

The method updates the ingredient category properties

### HTTP request

`GET https://joinposter.com/api/menu.updateCategoryIngredients`

### POST parameters of the menu.updateCategoryIngredients request

Parameter | Description
--------- | -----------
category_id | Ingredient category ID
category_name | Ingredient category new name

### The menu.updateCategoryIngredients response parameters

Parameter | Description
--------- | -----------
response | The updated ingredient category ID

