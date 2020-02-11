## dash.getClientsSales: Customer Sales

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/dash.getClientsSales'
  . '?token=687409:4164553abf6a031302898da7800b59fb'
  . '&dateFrom=20170920'
  . '&dateTo=20170922';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response":[
    {
      "client_id":"4",
      "firstname":"",
      "lastname":"Vladimir",
      "sum":"1030000",
      "profit":"825364",
      "profit_netto":"687803",
      "revenue":"907000",
      "clients":"3",
      "middle_invoice":3433.3333333333
    }
  ]
}
```

The method returns customer sales

### HTTP request

`GET https://joinposter.com/api/dash.getClientsSales`

### GET parameters of the dash.getClientsSales request

Parameter | Description
--------- | -----------
dateFrom | The sampling start date in the `Ymd` format. If it is not specified, the start date is one month later.
dateTo | The sampling end date in the `Ymd` format. If it is not specified, the end date is the current one.
interpolate | The output by hours, days, weeks, months. If not specified, the output is by day

### Parameters of the dash.getClientsSales response

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an array of objects. Each object contains the following parameters:

Parameter | Description
--------- | -----------
client_id | Customer ID
firstname | Customer first name
lastname | Customer last name
sum | Total amount of orders in kopecks
profit | Profit in kopecks
profit_netto | Profit without VAT in kopecks. Is returned if the 'Calculate cost and net profit' setting is enabled
revenue | Revenue amount in kopecks
clients | Order count
middle_invoice | The average check amount in rubles/hryvnias
