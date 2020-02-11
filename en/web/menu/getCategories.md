## menu.getCategories: List of Product Categories

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.getCategories'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&fiscal=0';

$data = sendRequest($url);
```

> Response example:

```json
{  
  "response":[  
    {  
      "category_id":"2",
      "category_name":"Sushi rolls",
      "category_photo":"/upload/pos_cdb_888/menu/category_1420674791_2.jpg",
      "parent_category":"0",
      "category_color":"white",
      "category_hidden":"0",
      "sort_order":"999",
      "fiscal":"0",
      "nodiscount":"0",
      "tax_id":"0",
      "left":"3",
      "right":"4",
      "category_tag": "sushi",
      "level":"1"
    }
  ]
}
```

The method returns a list of product categories

### HTTP request

`GET https://joinposter.com/api/menu.getCategories`

### GET parameters of the menu.getCategories request

Parameter | Description
--------- | -----------
fiscal | Fiscal category status: 0—non-fiscal, 1—fiscal. The default value is all categories.
id_1c | It allows returning in the response the product category ID in the 1C system. You must transmit true as a value. By default, it is not transmitted.

### The menu.getCategories response parameters

Parameter | Description
--------- | -----------
response | An array of objects

Inside the `response` parameter, there is an array, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
category_id | Category ID
category_name | Category name
category_photo | Category photo
parent_category | Parent category ID
category_color | Category color
category_hidden | The status of a hidden category: 0—not hidden, 1—hidden
sort_order | Sort order
fiscal | The status of a category being fiscal: 0—non-fiscal, 1—fiscal
nodiscount | Tha status of discounts applying: 0—do not apply, 1—apply
tax_id | Tax ID
left | The ID of the left category (by the Nested Set)
right | The ID of the right category (by the Nested Set)
level | Level of nesting of the category tree branch (by the Nested Set)
category_tag | The alleged product type in the category that was defined by machine learning algorithm. For example, `coffee`, `alcohol`, can be `null`.
id_1c | Product category ID in the 1C system

