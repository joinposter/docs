## finance.getTax: Tax Properties

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/finance.getTax'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&tax_id=3';

$data = sendRequest($url);
```

> Response example:

```json
{  
  "response":{  
    "tax_id":3,
    "country":"UA",
    "tax_name":"Налог с оборота",
    "tax_value":5,
    "type":2,
    "fiscal":1,
    "fiscal_program":0,
    "fixed":0,
    "delete":0
  }
}
```

The method returns tax properties

### HTTP GET request

`https://joinposter.com/api/finance.getTax`

### GET parameters of the finance.getTax request

Parameter | Description
--------- | -----------
tax_id | Tax ID

### The finance.getTax response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
tax_id | Tax ID
country | The two-letter country code in the ISO 3166 format
tax_name | Tax name
tax_value | Tax percentage
type | Tax type: 1—sales tax, 2—turnover tax, 3—VAT, 4—no tax
fiscal | Tax fiscality: 0—non-fiscal, 1—fiscal
fiscal_program | Program number on a fiscal printer
fixed | The status of the tax being flat: 0—non-flat, 1—flat
delete | The status of the tax having been removed: 0—removed, 1—not removed

