## storage.getReportMovement: Ingredients movements

>  Request example:

```php
<?
$url = 'https://joinposter.com/api/storage.getReportMovement'
  . '?token=687409:4164553abf6a031302898da7800b59fb'
  . '&dateFrom=20170101'
  . '&dateTo=20180101'
  . '&storage_id=1'
  . '&type=2';

$data = sendRequest($url);
```

> Response example:

```json
{
   "response":[
      {
         "ingredient_id":"332",
         "ingredient_name":"Borjome",
         "cost_start":13.63,
         "cost_end":13.63,
         "start":14,
         "income":0,
         "write_offs":0,
         "end":14
      },
      {
         "ingredient_id":"260",
         "ingredient_name":"Sprite",
         "cost_start":8.39,
         "cost_end":8.39,
         "start":2,
         "income":0,
         "write_offs":0,
         "end":2
      }
   ]
}
```

Request for the ingredients movements report

### HTTP request

`GET https://joinposter.com/api/storage.getReportMovement`

### GET-parameters of the storage.getReportMovement

Parameter | Description
-------- | --------
dateFrom | An optional parameter, the sampling start date in the `Ymd` format, inclusive. The default date is a month ago.
dateTo | An optional parameter, the sampling end date in the `Ymd` format, inclusive. The default date is the current date.
storage_id | An optional parameter, the storage ID to return the inventory checks to.
type | An optional parameter. Ingredients types: 1 — ingredient, 2 — product, 3 — product modifications, 4 — dish, 5 — preparation.

### The storage.getReportMovement response parameters

Parameter | Description
-------- | ---------
ingredient_id | A unique ingredient_id of the entity
ingredient_name | The name of an ingredient
cost_start | Average food cost of the ingredient at the date of the beginning of the sample in dollars
cost_end | Average food cost of the ingredient at the end of the sample in dollars
start | Beginning balance of the ingredient
income | Supplies of the ingredient
write_offs | Expense of the ingredient
end | End balance of the ingredient
