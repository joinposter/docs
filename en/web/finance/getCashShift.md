## finance.getCashShift: Register Shift Properties

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/finance.getCashShift'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&cash_shift_id=333';

$data = sendRequest($url);
```

> Response example:

```json
{  
  "response":{  
    "cash_shift_id":333,
    "spot_id":1,
    "timestart":1505977200000,
    "timeend":1505980800000,
    "amount_start":10000,
    "amount_end":10000,
    "amount_debit":0,
    "amount_sell_cash":0,
    "amount_sell_card":0,
    "amount_credit":0,
    "amount_collection":0,
    "user_id_start":3,
    "user_id_end":3,
    "comment":"бар"
  }
}
```

The method returns the register shift properties

### HTTP request

`GET https://joinposter.com/api/finance.getCashShift`

### GET parameters of the finance.getCashShift request

Parameter | Description
--------- | -----------
cash_shift_id | A mandatory parameter, the register shift ID

### The finance.getCashShift response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
cash_shift_id | Register shift ID
spot_id | Location ID
timestart | Date and time of register shift opening in a microtime format
timeend | Date and time of register shift closing in a microtime format
amount_start | Register amount at a register shift opening in kopecks
amount_end | Register amount at a register shift closing in kopecks
amount_debit | The amount of income in kopecks
amount_sell_cash | The amount of cash revenue in kopecks
amount_sell_card | The amount of non-cash revenue in kopecks
amount_credit | Amount of expenses in kopecks
amount_collection | Safe drop amount in kopecks
user_id_start | The ID of an employee who has opened a register shift
user_id_end | The ID of an employee who has closed a register shift
comment | Comment

