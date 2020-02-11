## finance.createCashShiftTransaction: Create a Register Shift Transaction

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/finance.createCashShiftTransaction'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$cash_shift_transaction = [
    'cash_shift_id' => 333,
    'type_id'       => 3,
    'category_id'   => 4,
    'user_id'       => 1,
    'amount'        => 499.99,
    'time'          => '2017-09-21 15:00',
    'is_fiscal'     => 1,
    'comment'       => 'Расход',
];

$data = sendRequest($url, 'post', $cash_shift_transaction);
```

> Response example:

```json
{  
  "response":{  
    "cash_shift_transaction_id":1649
  }
}
```

The method creates a register shift transaction

### HTTP request

`GET https://joinposter.com/api/finance.createCashShiftTransaction`

### POST parameters of the finance.createCashShiftTransaction request

Parameter | Description
--------- | -----------
cash_shift_id | Register shift ID
type_id | The register shift transaction type: 2—income, 3—expenditure, 4—safe drop.
category_id | The ID of the financial category. A mandatory property if the register shift transaction type is 2 or 3 and the account for cash is attached to the location.
user_id | Employee ID
amount | The register shift transaction amount
time | The date and time of the register shift transaction in the `Y-m-d H:i` format
is_fiscal | The status of the register-shift transaction being fiscal: 0—non-fiscal, 1—fiscal. The default value is 0.
comment | Comment

### The finance.createCashShiftTransaction response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
cash_shift_transaction_id | The register shift transaction ID

