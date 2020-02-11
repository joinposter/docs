## menu.createCategory: Create a Product Category

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.createCategory'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$category = [
    'category_name'   => 'Пицца',
    'parent_category' => 0,
    'category_color'  => 'yellow',
    'category_hidden' => 0,
    'tax_id'          => 0,
];

$data = sendRequest($url, 'post', $category);
```

> Response example:

```json
{  
  "response":52
}
```

The method creates a product category

### HTTP request

`GET https://joinposter.com/api/menu.createCategory`

### POST parameters of the menu.createCategory request

Parameter | Description
--------- | -----------
category_name | Product category name
parent_category | Parent category ID
category_color | Category color: white, red, orange, yellow, green, blue, navy blue, purple, black, mint blue, lime green, pink. The default color is white.
category_hidden | The status of a category being hidden: 0—not hidden, 1—hidden The default value is 0.
tax_id | Tax ID The default value is 0.

### The menu.createCategory response parameters

Parameter | Description
--------- | -----------
response | Created product category ID

