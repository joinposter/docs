## menu.getCategoriesIngredients: List of Ingredient Categories

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.getCategoriesIngredients'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&1c=true';

$data = sendRequest($url);
```

> Response example:

```json
{  
  "response":[  
    {  
      "category_id":"3",
      "name":"Алкоголь",
      "id_1c":"b80ffc81-0fc9-11e7-9ab4-ace01035e460"
    },
    {  
      "category_id":"2",
      "name":"Мясо",
      "id_1c":null
    },
    {  
      "category_id":"1",
      "name":"Овощи",
      "id_1c":null
    },
    {  
      "category_id":"4",
      "name":"Фрукты",
      "id_1c":null
    }
  ]
}
```

The method returns a list of ingredient categories

### HTTP request

`GET https://joinposter.com/api/menu.getCategoriesIngredients`

### GET parameters of the menu.getCategoriesIngredients request

Parameter | Description
--------- | -----------
1c | An optional parameter; if the value is `true`, it returns the product category ID in the 1C system in the response. By default, it is not transmitted.

### The menu.getCategoriesIngredients response parameters

Parameter | Description
--------- | -----------
response | An array of objects

Inside the `response` parameter, there is an array, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
category_id | Ingredient category ID
category_name | Ingredient category name
id_1c | Ingredient category ID in the 1C system

