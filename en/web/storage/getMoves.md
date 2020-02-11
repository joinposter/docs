## storage.getMoves: Get All Transfers

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/storage.getMoves'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);

```

> Response example:

```json
{
  "response":[
    {
      "moving_id":4,
      "date":"2017-11-16 21:34:00",
      "from_storage":1,
      "from_storage_name":"Склад Кухня",
      "to_storage":2,
      "to_storage_name":"Склад Бар",
      "user_id":7,
      "user_name":"Vladimir",
      "sum":150.65,
      "sum_netto":125.54
    }
  ]
}
```

The method returns all transfers

### HTTP request

`GET https://joinposter.com/api/storage.getMoves`

### GET parameters of the storage.getMoves request

Parameter | Description
--------- | -----------
dateFrom | An optional parameter, the sampling start date in the `Ymd` format, inclusive. The default date is a month ago.
dateTo | An optional parameter, the sampling end date in the `Ymd` format, inclusive. The default date is the current date.

### The storage.getMoves response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an array, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
moving_id | Transfer ID
date | Transfer date
from_stoarge | The ID of a storage the transfer has been made from
from_storage_name | The name of a storage the transfer has been made from
to_storge | The ID of a storage the transfer has been made to
to_storage_name | The name of a storage the transfer has been made to
user_id | The ID of a user who has made the transfer
user_name | The name of a user who has made the transfer
sum | The amount of transfer in hryvnias/rubles
sum_netto | The amount of transfer without VAT in hryvnias/rubles. Is returned if the 'Calculate cost and net profit' setting is enabled
