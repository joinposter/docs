## storage.getWastes: List of Manual Wastes

> Request example:

```php
<?
$url = 'https://joinposter.com/api/storage.getWastes'
  . '?token=687409:4164553abf6a031302898da7800b59fb'
  . '&dateFrom=20170101'
  . '&dateTo=20180101'
  . '&1c=true';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response": [
    {
      "waste_id": 1,
      "total_sum": 2800,
      "total_sum_netto": 2333,
      "user_id": 1,
      "storage_id": 1,
      "date": "2017-04-26 14:30:02",
      "reason_id": 0,
      "reason_name": null,
      "delete": 0
    },
    {
      "waste_id": 2,
      "total_sum": 791,
      "total_sum_netto": 659,
      "user_id": 1,
      "storage_id": 1,
      "date": "2017-04-26 15:21:12",
      "reason_id": 1,
      "reason_name": "Spoiled",
      "delete": 1
    }
  ]
}
```

The request for a list of all manual wastes.

### HTTP request

`GET https://joinposter.com/api/storage.getWastes`

### GET parameters of the storage.getWastes request

Parameter | Description
--------- | -----------
dateFrom | An optional parameter. The sampling start date (Ymd). The default date is a month ago.
dateTo | An optional parameter. The sampling end date (Ymd). The default date is the current date.
1c_id | An optional parameter. It allows returning manual wastes taking into account the removed ones (returns the delete flag). The value must be specified as true.

### The storage.getWastes response parameters

Parameter | Description
--------- | -----------
waste_id | Manual waste ID
total_sum | Total waste amount
total_sum_netto | Total waste amount without VAT. Is returned if the 'Calculate cost and net profit' setting is enabled
user_id | The ID of the user who has made the waste
storage_id | The ID of the storage the waste has been made from
date | Waste date
reason_id | Waste reason ID
reason_name | Waste reason
delete | The status of the waste having been removed: 1—removed, 0—not removed
