## menu.getCategory: Product Category Properties

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.getCategory'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&category_id=30'
 . '&1c=true';

$data = sendRequest($url);
```

> Response example:

```json
{  
  "response":{  
    "category_id":30,
    "category_name":"Бар",
    "category_photo":null,
    "category_photo_origin":null,
    "parent_category":0,
    "category_color":"yellow",
    "category_hidden":0,
    "sort_order":3,
    "fiscal":0,
    "nodiscount":0,
    "tax_id":2,
    "left":7,
    "right":42,
    "level":1,
    "category_tag":"alco",
    "visible": [
      {
        "spot_id": 1,
        "visible": 1
      },
      {
        "spot_id": 2,
        "visible": 0
      }
    ],
    "id_1c":"9c68dbc9-b255-11e6-9a8f-ace01035e460"
  }
}
```

The method returns the product category properties

### HTTP request

`GET https://joinposter.com/api/menu.getCategory`

### GET parameters of the menu.getCategory request

Parameter | Description
--------- | -----------
category_id | Category ID
1c | It allows returning in the response the product category ID in the 1C system. You must transmit true as a value. By default, it is not transmitted.

### menu.getCategory response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
category_id | Category ID
category_name | Category name
category_photo | Category photo
category_photo_origin | Uploaded photo original
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
visible | The array, each object of which has a sign of category visibility in the venue.
id_1c | Product category ID in the 1C system

Inside the `visible` parameter, there is an array, each element of which contains the following parameters:

Parameter | Description
-------- | --------
spot_id | Venue ID
visible | The sign that shows if the category in this venue is visible: 0 — hidden, 1 — visible

