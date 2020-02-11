## finance.createCategory: Create a New Financial Category

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/finance.createCategory'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$category = [
    'category_name'     => 'Коммуналка',
    'category_parent'   => 0,
    'operations_in'     => 0, 
    'operations_out'    => 1

];

$data = sendRequest($url, 'post', $category);
```

> Response example:

```json
{
  "response":6
}
```

The method creates a new financial category

### HTTP request

`POST https://joinposter.com/api/finance.createCategory`

### POST parameters of the finance.createCategory request

Parameter | Description
--------- | -----------
category_name | Category name
category_parent | The parent category ID; if it is 0, the current category will be displayed at the top level
operations_in | The income-type transactions being valid: 1—valid, 0—not valid
operations_out | The expenditure-type transactions being valid: 1— valid, 0—not valid

### The finance.createCategory response parameters

Parameter | Description
--------- | -----------
response | The created category ID

