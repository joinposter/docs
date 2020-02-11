## dash.getSpotsSales: Location Sales

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/dash.getSpotsSales'
  . '?token=687409:4164553abf6a031302898da7800b59fb'
  . '&dateFrom=20170905'
  . '&dateTo=20170908';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response":{
    "revenue":536723.37,
    "profit":448025.64,
    "profit_netto":373354.7,
    "clients":423,
    "middle_invoice":1268.8495744681
  }
}
```

The method returns location sales

### HTTP request

`GET https://joinposter.com/api/dash.getSpotsSales`

### GET parameters of the dash.getSpotsSales request

Parameter | Description
--------- | -----------
dateFrom | An optional parameter, the sampling start date in the `Ymd` format, inclusive. The default date is a month ago.
dateTo | An optional parameter, the sampling end date in the `Ymd` format, inclusive. The default date is the current date.
spot_id | An optional parameter, the location ID to return reports to If it is not specified, all locations will be displayed.

### Parameters of the dash.getSpotsSales response

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
revenue | Revenue amount in kopecks
profit | Profit in kopecks
profit_netto | Profit without VAT in kopecks. Is returned if the 'Calculate cost and net profit' setting is enabled
clients | Order count
middle_invoice | The average check amount in rubles/hryvnias
