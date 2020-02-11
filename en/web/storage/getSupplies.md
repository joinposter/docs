## storage.getSupplies: Get All Supplies

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/storage.getSupplies'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response":[
    {
      "supply_id":"48",
      "storage_id":"1",
      "supplier_id":"1",
      "date":"2017-11-17 08:09:33",
      "supply_sum":"1800",
      "supply_sum_netto":"1500",
      "supply_comment":"",
      "storage_name":"Склад Кухня",
      "supplier_name":"Закупщик",
      "delete":"1",
      "account_id":null
    },
    {
      "supply_id":"47",
      "storage_id":"1",
      "supplier_id":"1",
      "date":"2017-05-18 09:11:00",
      "supply_sum":"300000",
      "supply_sum_netto":"250000",
      "supply_comment":"",
      "storage_name":"Склад Кухня",
      "supplier_name":"Закупщик",
      "delete":"0",
      "account_id":null
    },
    {
      "supply_id":"46",
      "storage_id":"1",
      "supplier_id":"1",
      "date":"2017-05-18 09:07:00",
      "supply_sum":"669882890",
      "supply_sum_netto":"558235742",
      "supply_comment":"",
      "storage_name":"Склад Кухня",
      "supplier_name":"Закупщик",
      "delete":"0",
      "account_id":null
    }
  ]
}
```

The method returns all supplies

### HTTP request

`GET https://joinposter.com/api/storage.getSupplies`

### GET parameters of the storage.getSupplies request

Parameter | Description
--------- | -----------
dateFrom | An optional parameter, the sampling start date in the `Ymd` format, inclusive. The default date is a month ago.
dateTo | An optional parameter, the sampling end date in the `Ymd` format, inclusive. The default date is the current date.
limit | An optional parameter, the number of supplies to be got. If `dateFrom` and `dateTo` are used, this parameter is ignored.
offset | An optional parameter, the number of entries to be skipped from the top of the list. By default, all supplies will be displayed. If `dateFrom` and `dateTo` are used, this parameter is ignored.

### The storage.getSupplies response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an array, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
supply_id | Supply ID
storage_id | Storage ID the supply has been made to
supplier_id | Supplier ID
date | Supply date
account_id | Financial account ID the supply has been wasted from
supply_sum | Supply amount in kopecks
supply_sum_netto | Supply amount without VAT in kopecks. Is returned if the 'Calculate cost and net profit' setting is enabled
supply_comment | Comment
storage_name | Storage name
supplier_name | Supplier name
delete | The status of the supply having been removed: 1—removed, 0—not removed
