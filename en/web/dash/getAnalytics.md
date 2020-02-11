## dash.getAnalytics: Sales Reports

> Request example:

```php
<?php

$url = 'https://joinposter.com/api/dash.getAnalytics' 
    . '?format=json'
    . '&token=687409:4164553abf6a031302898da7800b59fb'
    . '&dateFrom=20171009'
    . '&dateTo=20171012'
    . '&interpolate=week'
    . '&type=waiters';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response":{
    "data":[
      "169255.7100",
      "160327.7300",
      "48259.0100",
      "1470.0000"
    ],
    "data_hourly":[
      "36520.2400",
      "17785.4500",
      "19163.5600",
      "12688.5200",
      0,
      0,
      0,
      0,
      "13747.4500",
      "19465.3900",
      "8701.5900",
      "12727.5300",
      "12029.0000",
      "18482.3600",
      "18391.7200",
      "25149.2900",
      "23136.1600",
      "15255.1100",
      "14300.2800",
      "17448.0000",
      "28419.3000",
      "23969.5500",
      "19392.5800",
      "22539.3700"
    ],
    "data_weekday":[
      0,
      "169255.7100",
      "160327.7300",
      "48259.0100",
      "1470.0000",
      0,
      0
    ],
    "counters":{
      "revenue":"379312.4500",
      "profit":"315131.6900",
      "transactions":"248",
      "visitors":"744",
      "average_receipt":1535.6779352227,
      "average_time":"125.76268347"
    }
  }
}
```

```php
<?php

$url = 'https://joinposter.com/api/dash.getAnalytics'
    . '?format=json'
    . '&token=687409:4164553abf6a031302898da7800b59fb'
    . '&dateFrom=20171009'
    . '&dateTo=20171012'
    . '&interpolate=week'
    . '&type=waiters';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response":[
    {
      "user_id":"2",
      "name":"Максим",
      "sum":"5248550",
      "profit":"4505024",
      "revenue":"5522290",
      "clients":"42",
      "middle_time":"1871214.0370"
    },
    {
      "user_id":"6",
      "name":"Антон",
      "sum":"5873540",
      "profit":"5187174",
      "revenue":"6234086",
      "clients":"42",
      "middle_time":"3.2910"
    }
  ]
}
```

The method returns the sales reports

### HTTP request

`GET https://joinposter.com/api/dash.getAnalytics`

### GET parameters of the dash.getAnalytics request

Parameter | Description
--------- | -----------
dateFrom | An optional parameter, the period start date in the `Ymd` format. If it is not specified, all sales for the last thirty days from `dateTo` will be displayed.
dateTo | An optional parameter, the period end date in the `Ymd` format. The default date is current.
interpolate | An optional parameter, an output by days—day, weeks—week, months—month. By default, it’s `day`.
select | An optional parameter, sampling types: revenue—`revenue`, profit—`profit`, an average check—`average_receipt`, orders count—`transactions`, customer count—`visitors`, average time—`average_time`. By default, it’s `revenue`.
type | An optional parameter, type of reports: by waiter—waiters, station—workshops, category—category, product—products, location—spots, customer—clients. The default value is All.
id | An optional parameter, an ID of the entity by which the sampling will return, for example, an ID of a waiter, a station, a category, a product, a location, a customer. The default value is All.
business_day | If it is `true,` the sales reports will be returned by the business day the `dateFrom` time fits into. The default value is `false`.

The response format depends on the value of the `type` parameter.

### Parameters of the dash.getAnalytics response if the type is waiters

Inside the `response` parameter, there is an array with objects. Each object contains such parameters as:

Parameter | Description
--------- | -----------
user_id | Employee ID
name | Employee name
sum | The amount of all products for orders for the current waiter in hryvnias
profit | Total revenue by bills
revenue | The amount of bills paid
clients | Сlosed orders count
middle_time | Average order service time

### Dash.getAnalytics response parameters if the type is clients

Inside the `response` parameter, there is an array with objects. Each object contains such parameters as:

Parameter | Description
--------- | -----------
client_id | Customer ID
firstname | Customer first name
lastname | Customer last name
sum | The amount of all products in each order in kopecks
profit | Total revenue by bills
revenue | The actual amount of bills paid in kopecks
payed_cash | The amount paid by cash
payed_card | The amount paid by credit cards
payed_third_party | The total amount of payments via external services
clients | Сlosed orders count
phone | Customer phone number
email | Email

### Dash.getAnalytics response parameters if type is workshops, category, products, spots

Inside the `response` parameter, there is an object with the following parameters:

Parameter | Description
--------- | -----------
data | The sales amounts array grouped according to the `interpolate` and `type` parameters
data_hourly | The values array structured by hours. The amount in hryvnias.
data_weekday | The sales amounts array structured by days of the week. The amount in hryvnias.
counters | Counters of key indicators for a given period. The amount in hryvnias.
transaction_id | Transaction ID.

Inside the `counters` parameter, there is an object with the following parameters:

Parameter | Description
--------- | -----------
revenue | Revenues in hryvnias
profit | Profit in hryvnias
transactions | Check count
visitors | Seat count
average_receipt | An average check in hryvnias
average_time | Average check closure time in minutes

