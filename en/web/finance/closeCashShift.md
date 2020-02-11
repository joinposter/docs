## finance.closeCashShift: Close a Register Shift

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/finance.closeCashShift'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$cash_shift = [
    'cash_shift_id' => 335,
    'user_id'       => 3,
    'amount'        => 234.56,
    'time'          => '2017-09-21 20:00',
    'is_fiscal'     => 1,
    'comment'       => 'бар',
];

$data = sendRequest($url, 'post', $cash_shift);
```

> Response example:

```json
{  
  "response":true
}
```

The method closes a register shift

### HTTP request

`POST https://joinposter.com/api/finance.closeCashShift`

### POST parameters of the finance.closeCashShift request

Parameter | Description
--------- | -----------
cash_shift_id | Register shift ID
user_id | Employee ID
amount | Register amount at a register shift closing in hryvnias/rubles
time | Date and time of register shift closing down to the minute in the `Y-m-d H:i` format
is_fiscal | The status of the register-shift closing transaction being fiscal: 0—non-fiscal, 1—fiscal. The default value is 0.
comment | Register shift comment. By default, it is not transmitted.

### The finance.closeCashShift response parameters

Parameter | Description
--------- | -----------
response | true if the register shift has been successfully closed

