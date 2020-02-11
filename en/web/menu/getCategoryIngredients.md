## menu.getCategoryIngredients: Ingredient Category Properties

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.getCategoryIngredients'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&category_id=3'
 . '&1c=true';

$data = sendRequest($url);
```

> Response example:

```json
{  
  "response":{  
    "category_id":"3",
    "name":"Алкоголь",
    "id_1c":"b80ffc81-0fc9-11e7-9ab4-ace01035e460"
  }
}
```

The method returns the ingredient category properties

### HTTP request

`GET https://joinposter.com/api/menu.getCategoryIngredients`

### GET parameters of the menu.getCategoryIngredients request

Parameter | Description
--------- | -----------
category_id | Ingredient category ID
1c | An optional parameter; if the value is `true`, it returns the product category ID in the 1C system in the response. By default, it is not transmitted.

### The menu.getCategoryIngredients response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
category_id | Ingredient category ID
category_name | Ingredient category name
id_1c | Ingredient category ID in the 1C system

