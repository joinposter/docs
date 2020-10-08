## dash.getWaitersSales: Waiter Sales

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/dash.getWaitersSales'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&dateFrom=20170901';

$data = sendRequest($url);
```

> Response example:

```json 
{
  "response":[
    {
      "user_id":"1",
      "name":"Demo",
      "profit":"153707331",
      "profit_netto":"128089443",
      "revenue":"186224294",
      "clients":"1414",
      "middle_time":49364.020916667,
      "middle_invoice":1317.0034936351
    },
    {
      "user_id":"2",
      "name":"Максим",
      "profit":"147406757",
      "profit_netto":"122838964",
      "revenue":"179108697",
      "clients":"1314",
      "middle_time":58078.986483333,
      "middle_invoice":1363.0798858447
    },
    {
      "user_id":"6",
      "name":"Антон",
      "profit":"155127873",
      "profit_netto":"129273228",
      "revenue":"188413623",
      "clients":"1424",
      "middle_time":1.8170166666667,
      "middle_invoice":1323.129375
    }
  ]
}
```

The method returns waiter sales

### HTTP request

`GET https://joinposter.com/api/dash.getWaitersSales`

### GET parameters of the dash.getWaitersSales request

Parameter | Description
--------- | -----------
dateFrom | An optional parameter, the sampling start date in the `Ymd` format, includes the specified day. The default date is a month ago.
dateTo | An optional parameter, the sampling end date in the `Ymd` format, includes the specified day. The default date is the current date.

### Parameters of the dash.getWaitersSales response

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
user_id | Waiter ID
name | Waiter’s name
revenue | Revenue amount in kopecks
profit | Profit in kopecks
profit_netto | Profit without VAT in kopecks. Is returned if the 'Calculate cost and net profit' setting is enabled
clients | Closed orders count
middle_invoice | An average check in hryvnias/rubles
middle_time | Total time spent on service in minutes
worked_time | Worked time, waiter’s in minutes
