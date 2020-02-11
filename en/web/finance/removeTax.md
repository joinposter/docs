## finance.removeTax: Remove a Tax

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/finance.removeTax'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$tax = [
    'tax_id' => 3,
];

$data = sendRequest($url, 'post', $tax);
```

> Response example:

```json
{  
  "response":true
}
```

The method removes a tax

### HTTP POST request

`https://joinposter.com/api/finance.removeTax`

### POST parameters of the finance.removeTax request

Parameter | Description
--------- | -----------
tax_id | Tax ID

### The finance.removeTax response parameters

Parameter | Description
--------- | -----------
response | true if the tax has been successfully removed

