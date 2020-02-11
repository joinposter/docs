## finance.updateTax: Update Tax Properties

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/finance.updateTax'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$tax = [
    'tax_id' => 3,
    'name'   => 'Налог с оборота',
    'value'  => 10,
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

The method updates the tax properties

### HTTP POST request

`https://joinposter.com/api/finance.updateTax`

### POST parameters of the finance.updateTax request

Parameter | Description
--------- | -----------
tax_id | Tax ID
name | Tax name
value | Tax percentage
type | Tax type: 1—sales tax, 2—turnover tax, 3—VAT, 4—no tax
fiscal | Tax fiscality: 0—non-fiscal, 1—fiscal. The default value is 0.
fiscal_program | Program number on a fiscal printer. The default value is 0.

### The finance.updateTax response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
tax_id | The updated tax ID

