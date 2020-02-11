## dash.getCategoriesSales: Category Sales

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/dash.getCategoriesSales'
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
      "revenue":"38568300",
      "profit":"36307114",
      "profit_netto":"30255928",
      "count":"1173",
      "category_name":"Вторые блюда",
      "category_id":"33"
    },
    {
      "revenue":"36970440",
      "profit":"21885184",
      "profit_netto":"18237653",
      "count":"863",
      "category_name":"Главный экран",
      "category_id":0
    },
    {
      "revenue":"34474000",
      "profit":"31377831",
      "profit_netto":"26148193",
      "count":"830",
      "category_name":"Салаты",
      "category_id":"31"
    },
    {
      "revenue":"33876200",
      "profit":"31379225",
      "profit_netto":"26149354",
      "count":"905",
      "category_name":"Торты",
      "category_id":"37"
    },
    {
      "revenue":"22781920",
      "profit":"18568329",
      "profit_netto":"15473608",
      "count":"1173",
      "category_name":"Кофе",
      "category_id":"10"
    }
  ]
}
```

The method returns category sales

### HTTP request

`GET https://joinposter.com/api/dash.getCategoriesSales`

### GET parameters of the dash.getCategoriesSales request

Parameter | Description
--------- | -----------
dateFrom | The sampling start date in the `Ymd` format. If it is not specified, the start date is one month later.
dateTo | The sampling end date in the `Ymd` format. If it is not specified, the end date is the current one.
spot_id | The location ID; if it is not specified, all locations will be displayed

### Parameters of the dash.getCategoriesSales response

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an array of objects. Each object contains the following parameters:

Parameter | Description
--------- | -----------
revenue | Revenue amount in kopecks
profit | Profit amount in kopecks
profit_netto | Profit amount without VAT in kopecks. Is returned if the 'Calculate cost and net profit' setting is enabled
count | Sales count
category_name | Category name
category_id | Category ID
