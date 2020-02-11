## finance.createTax: Create a Tax

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/finance.createTax'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$tax = [
    'name'   => 'Налог с оборота',
    'value'  => 5,
    'type'   => 2,
    'fiscal' => 1,
];

$data = sendRequest($url, 'post', $tax);
```

> Response example:

```json
{  
  "response":{  
    "tax_id":3
  }
}
```

The method creates a tax

### HTTP POST request

`https://joinposter.com/api/finance.createTax`

### POST parameters of the finance.createTax request

Parameter | Description
--------- | -----------
name | Tax name
value | Tax percentage
type | Tax type: 1—sales tax, 2—turnover tax, 3—VAT, 4—no tax
fiscal | Tax fiscality: 0—non-fiscal, 1—fiscal. The default value is 0.
fiscal_program | Program number on a fiscal printer. The default value is 0.

### The finance.createTax response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
tax_id | The created tax ID

