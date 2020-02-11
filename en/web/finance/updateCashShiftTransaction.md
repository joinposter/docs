## finance.updateCashShiftTransaction: Update the Register Shift Transaction Properties

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/finance.updateCashShiftTransaction'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$cash_shift_transaction = [
    'cash_shift_transaction_id' => 611,
    'type_id'                   => 3,
    'category_id'               => 4,
    'user_id'                   => 3,
    'amount'                    => 499.99,
    'time'                      => '2017-09-21 15:00',
    'is_fiscal'                 => 1,
    'comment'                   => 'Waste',
];

$data = sendRequest($url, 'post', $cash_shift_transaction);
```

> Response example:

```json
{  
  "response":{  
    "cash_shift_transaction_id":1650
  }
}
```

The method updates the register shift transaction properties

!>     The “opening” and “closing” transaction types cannot be updated.
### HTTP request

`GET https://joinposter.com/api/finance.updateCashShiftTransaction`

### POST parameters of the finance.updateCashShiftTransaction request

Parameter | Description
--------- | -----------
cash_shift_transaction_id | The register shift transaction ID
type_id | The register shift transaction type: 1—opening, 2—income, 3—expenditure, 4—safe drop, 5—closing. Types 1 and 5 cannot be updated. By default, it takes the previous value of the register-shift transaction being edited.
category_id | The ID of the financial category. A mandatory property if the register shift transaction type is 2 or 3 and an account for cash is attached to the location. By default, it takes the previous value of the register-shift transaction being edited.
user_id | Employee ID. By default, it takes the previous value of the register-shift transaction being edited.
amount | The register shift transaction amount. By default, it takes the previous value of the register-shift transaction being edited.
time | The date and time of the register shift transaction in the “Y-m-d H:i” format. By default, it takes the previous value of the register-shift transaction being edited.
is_fiscal | The status of the register-shift transaction being fiscal: 0—non-fiscal, 1—fiscal. By default, it takes the previous value of the register-shift transaction being edited.
comment | Comment. By default, it takes the previous value of the register-shift transaction being edited.

### The finance.updateCashShiftTransaction response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
cash_shift_transaction_id | The register shift transaction new ID

