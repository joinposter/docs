## finance.getCashShifts: Register Shift List

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/finance.getCashShifts'
    . '?token=687409:4164553abf6a031302898da7800b59fb'
    . '&dateFrom=20170701'
    . '&dateTo=20170901'
    . '&timezone=client';

$data = sendRequest($url);
```

> Response example:

```json
{  
  "response":[  
    {  
      "cash_shift_id":333,
      "spot_id":1,
      "timestart":1505977200000,
      "timeend":1505980800000,
      "date_start": "2018-10-18 13:45:46",
      "date_end": "2018-10-18 23:00:00",
      "amount_start":10000,
      "amount_end":10000,
      "amount_debit":0,
      "amount_sell_cash":0,
      "amount_sell_card":0,
      "amount_credit":0,
      "amount_collection":0,
      "user_id_start":3,
      "user_id_end":3,
      "comment":"бар",
      "spot_name":"Киоск",
      "spot_adress":"ул. Вокзальная, 12",
      "table_num":"0"
    }
  ]
}
```

The method returns a list of register shifts

### HTTP request

`GET https://joinposter.com/api/finance.getCashShifts`

### GET parameters of the finance.getCashShifts request

Parameter | Description
--------- | -----------
spot_id | An optional parameter, the ID of a location to return reports to
dateFrom | An optional parameter, the sampling start date in the `Ymd` format, inclusive. The default date is a month ago.
dateTo | An optional parameter, the sampling end date in the `Ymd` format, inclusive. The default date is the current date.
timezones | An optional parameter; if it equals `client`, the date_start and date_end are returned in the account time zone.

### The finance.getCashShifts response parameters

Parameter | Description
--------- | -----------
response | An array of register shifts

Inside the `response` parameter, there is an array, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
cash_shift_id | Register shift ID
spot_id | Location ID
timestart | Date and time of register shift opening in a microtime format
timeend | Date and time of register shift closing in a microtime format
date_start | Date and time of register shift opening in the “Y-m-d H:i:s” format
date_end | Date and time of register shift closing in the “Y-m-d H:i:s” format
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
spot_name | Location name
spot_adress | Location address

