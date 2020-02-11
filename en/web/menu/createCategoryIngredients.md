## menu.createCategoryIngredients: Create an Ingredient Category

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.createCategoryIngredients'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$category_ingredients = [
    'category_name' => 'Овощи',
];

$data = sendRequest($url, 'post', $category_ingredients);
```

> Response example:

```json
{  
  "response":27
}
```

The method creates an ingredient category

### HTTP request

`GET https://joinposter.com/api/menu.createCategoryIngredients`

### POST parameters of the menu.createCategoryIngredients request

Parameter | Description
--------- | -----------
category_name | Ingredient category name

### The menu.createCategoryIngredients response parameters

Parameter | Description
--------- | -----------
response | The created ingredient category ID

