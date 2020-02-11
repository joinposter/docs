## finance.removeCashShiftTransaction: Remove the Register Shift Transaction

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/finance.removeCashShiftTransaction'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$cash_shift_transaction = [
    'cash_shift_transaction_id' => 611,
];

$data = sendRequest($url, 'post', $cash_shift_transaction);
```

> Response example:

```json
{  
  "response":true
}
```

The method removes a register shift transaction.

!>     You can only remove a register-shift transaction with an “Income,” “Expenditure,” or “Safe drop” type

### HTTP request

`GET https://joinposter.com/api/finance.removeCashShiftTransaction`

### POST parameters of the finance.removeCashShiftTransaction request

Parameter | Description
--------- | -----------
cash_shift_transaction_id | The register shift transaction ID

### The finance.removeCashShiftTransaction response parameters

Parameter | Description
--------- | -----------
response | true if the register-shift transaction has been successfully removed

