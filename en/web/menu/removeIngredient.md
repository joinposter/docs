## menu.removeIngredient: Remove an Ingredient

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.removeIngredient'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$ingredient = [
    'ingredient_id' => 811,
];

$data = sendRequest($url, 'post', $ingredient);
```

> Response example:

```json
{  
  "response":true
}
```

The method removes an ingredient

### HTTP request

`GET https://joinposter.com/api/menu.removeIngredient`

### POST parameters of the menu.removeIngredient request

Parameter | Description
--------- | -----------
ingredient_id | Ingredient ID

### The menu.removeIngredient response parameters

Parameter | Description
--------- | -----------
response | true if the ingredient has been successfully removed

