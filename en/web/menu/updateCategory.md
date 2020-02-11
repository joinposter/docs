## menu.updateCategory: Update the Product Category Properties

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.updateCategory'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$category = [
    'category_id'     => 34,
    'category_name'   => 'Пицца',
    'parent_category' => 0,
    'category_color'  => 'red',
];

$data = sendRequest($url, 'post', $category);
```

> Response example:

```json
{  
  "response": 34
}
```

The method updates the product category properties

### HTTP request

`GET https://joinposter.com/api/menu.updateCategory`

### POST parameters of the menu.updateCategory request

Parameter | Description
--------- | -----------
category_id | Product category ID
category_name | Product category name
parent_category | Parent category ID
category_color | Category color: white, red, orange, yellow, green, blue, navy blue, purple, black, mint blue, lime green, pink. By default, it is not transmitted.
category_hidden | The status of a category being hidden: 0—not hidden, 1—hidden By default, it is not transmitted.
tax_id | Tax ID By default, it is not transmitted.

### The menu.updateCategory response parameters

Parameter | Description
--------- | -----------
response | The updated product category ID

