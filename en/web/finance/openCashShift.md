## finance.openCashShift: Open a Register Shift

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/finance.openCashShift'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$cash_shift = [
    'spot_id'   => 1,
    'user_id'   => 1,
    'amount'    => 123.45,
    'time'      => '2017-09-21 10:00',
    'is_fiscal' => 1,
];

$data = sendRequest($url, 'post', $cash_shift);
```

> Response example:

```json
{  
  "response":{  
    "cash_shift_id":333
  }
}
```

The method opens a register shift

### HTTP request

`GET https://joinposter.com/api/finance.openCashShift`

### POST parameters of the finance.openCashShift request

Parameter | Description
--------- | -----------
spot_id | Location ID
user_id | Employee ID
amount | Register amount at a register shift opening in hryvnias/rubles
time | Date and time of register shift opening in minutes in a `Y-m-d H:i` format
is_fiscal | The status of the register-shift opening transaction being fiscal: 0—non-fiscal, 1—fiscal. The default value is 0.

### The finance.openCashShift response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
cash_shift_id | The ID of an open register shift

