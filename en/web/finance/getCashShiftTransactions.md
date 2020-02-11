## finance.getCashShiftTransactions: A Register Shift Transaction List

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/finance.getCashShiftTransactions'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&shift_id=333';

$data = sendRequest($url);
```

> Response example:

```json
{  
  "response":[  
    {  
      "shift_tr_id":1648,
      "shift_id":333,
      "time":1505980800000,
      "type":5,
      "tr_amount":10000,
      "user_id":3,
      "comment":"бар",
      "shift_tr_id_edit":0,
      "user_id_edit":0,
      "edit_time":0,
      "edit":0,
      "delete":0,
      "is_fiscal":0
    },
    {  
      "shift_tr_id":1647,
      "shift_id":333,
      "time":1505977200000,
      "type":1,
      "tr_amount":10000,
      "user_id":3,
      "comment":"",
      "shift_tr_id_edit":0,
      "user_id_edit":0,
      "edit_time":0,
      "edit":0,
      "delete":0,
      "is_fiscal":1
    }
  ]
}
```

The method returns a list of register-shift transactions

### HTTP request

`GET https://joinposter.com/api/finance.getCashShiftTransactions`

### GET parameters of the finance.getCashShiftTransactions request

Parameter | Description
--------- | -----------
shift_id | A mandatory parameter, the ID of the register shift to return transactions to

### The finance.getCashShiftTransactions response parameters

Parameter | Description
--------- | -----------
response | An array of the register shift transactions

Inside the `response` parameter, there is an array, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
shift_tr_id | The register shift transaction ID
shift_id | Register shift ID
time | Date and time of the register shift transaction in a microtime format
type | The register shift transaction type: 1—opening, 2—income, 3—expenditure, 4—safe drop, 5—closing.
tr_amount | The register shift transaction amount
user_id | Employee ID
comment | Comment
shift_tr_id_edit | The ID of the register shift transaction the editing has been from. If there has been no editing, it returns 0.
user_id_edit | The ID of an employee who has edited a register shift transaction. If there has been no editing, it returns 0.
edit_time | The time of editing a register shift transaction. If there has been no editing, it returns 0.
edit | The status of a register shift transaction being edited: 0—not edited, 1—edited.
delete | The status of a register shift transaction being removed: 0—not removed, 1—removed.
is_fiscal | The status of the register-shift transaction being fiscal: 0—non-fiscal, 1—fiscal.

