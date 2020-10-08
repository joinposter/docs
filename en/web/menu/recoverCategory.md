## menu.recoverCategory: Recover a Category

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.recoverCategory'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$category = [
    'category_id' => 48,
    'parent_category_id' => 10,
];

$data = sendRequest($url, 'post', $category);
```

> cURL example:

```php
curl -X POST \
  'http://poster.pos/api/menu.recoverCategory?token=687409:4164553abf6a031302898da7800b59fb' \
  -H 'cache-control: no-cache' \
  -H 'content-type: multipart/form-data \
  -F category_id=38 \
  -F parent_category_id=5 \

```

> Response example:

```json
{  
  "response":true
}
```

The method recovers a category

### POST parameters of the menu.recoverCategory request

Parameter | Description
--------- | -----------
category | Category ID, required
parent_category_id | parent menu category ID

### The menu.recoverCategory response parameters

Parameter | Description
--------- | -----------
response | true if the category has been successfully recovered

