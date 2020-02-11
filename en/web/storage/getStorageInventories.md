## storage.getStorageInventories: Get the Storage Inventory History

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/storage.getStorageInventories'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&storage_id=1';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response":[
    {
      "inventory_id":"3",
      "storage_id":"1",
      "date_start":"2015-08-12 19:07:08",
      "date_end":"2017-05-18 09:10:31",
      "date_set":"0000-00-00 00:00:00",
      "date_inventory":"2017-05-18 09:10:31",
      "sum":"871875648398",
      "sum_netto":"726563040332",
      "inventory_status":"1"
    },
    {
      "inventory_id":"2",
      "storage_id":"1",
      "date_start":"2015-02-05 13:10:26",
      "date_end":"2015-08-12 19:07:08",
      "date_set":"0000-00-00 00:00:00",
      "date_inventory":"0000-00-00 00:00:00",
      "sum":"104384",
      "sum_netto":"86987",
      "inventory_status":"1"
    },
    {
      "inventory_id":"1",
      "storage_id":"1",
      "date_start":"2013-08-09 16:30:13",
      "date_end":"2015-02-05 13:10:26",
      "date_set":"0000-00-00 00:00:00",
      "date_inventory":"0000-00-00 00:00:00",
      "sum":"-21236",
      "sum_netto":"-17697",
      "inventory_status":"1"
    }
  ]
}
```

The method returns a storage inventory history

### HTTP request

`GET https://joinposter.com/api/storage.getStorageInventories`

### GET parameters of the storage.getStorageInventories request

Parameter | Description
--------- | -----------
storage_id | A mandatory parameter, the storage ID to return the inventory checks to

### The storage.getStorageInventories response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an array, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
inventory_id | Inventory check ID
storage_id | Storage ID
data_start | Inventory check start date
data_end | Inventory check end date
date_set | Backdating date. If the inventory check was backdated, it corresponds to `date_end`.
data_inventory | The inventory check actual date
sum | Total amount of the inventory check product food cost in kopecks
sum_netto | Total amount of the inventory check product food cost without VAT in kopecks. Is returned if the 'Calculate cost and net profit' setting is enabled
inventory_status | Inventory check status: 1—conducted, 0—not conducted
