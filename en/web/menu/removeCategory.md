## menu.removeCategory: Remove a Product Category

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.removeCategory'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$category = [
    'category_id' => 52,
];

$data = sendRequest($url, 'post', $category);
```

> Response example:

```json
{  
  "response":true
}
```

The method removes a product category

### HTTP request

`GET https://joinposter.com/api/menu.removeCategory`

### POST parameters of the menu.removeCategory request

Parameter | Description
--------- | -----------
category_id | Product category ID

### The menu.removeCategory response parameters

Parameter | Description
--------- | -----------
response | true if the product category has been successfully removed

