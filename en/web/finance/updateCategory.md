## finance.updateCategory: Update a Financial Category

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/finance.updateCategory'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$category = [
    'category_id'       => 13,
    'category_name'     => 'Коммуналка',
    'category_parent'   => 0,
    'operations_in'     => 1, 
    'operations_out'    => 1,

];

$data = sendRequest($url, 'post', $category);
```

> Response example:

```json
{
  "response":13
}
```

The method updates a financial category

### HTTP request

`POST https://joinposter.com/api/finance.updateCategory`

### POST parameters of the finance.updateCategory request

Parameter | Description
--------- | -----------
category_id | The ID of the category being updated
category_name | Category name
category_parent | The parent category ID; if it is 0, the current category will be displayed at the top level
operations_in | The income-type transactions being valid: 1—valid, 0—not valid
operations_out | The expenditure-type transactions being valid: 1— valid, 0—not valid

### The finance.updateCategory response parameters

Parameter | Description
--------- | -----------
response | The updated category ID

