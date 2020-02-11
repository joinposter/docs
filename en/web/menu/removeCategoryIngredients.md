## menu.removeCategoryIngredients: Remove the Ingredient Category

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.removeCategoryIngredients'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$category_ingredients = [
    'category_id'      => 2,
    'with_ingredients' => 1,
];

$data = sendRequest($url, 'post', $category_ingredients);
```

> Response example:

```json
{  
  "success":"successful delete category"
}
```

The method removes the ingredient category

### HTTP request

`GET https://joinposter.com/api/menu.removeCategoryIngredients`

### POST parameters of the menu.removeCategoryIngredients request

Parameter | Description
--------- | -----------
category_id | Ingredient category ID
with_ingredients | The status of removing ingredients in the category: 0—not to remove, 1—remove. The default value is 0.

### The menu.removeCategoryIngredients response parameters

Parameter | Description
--------- | -----------
success | A successful removal notification

