## storage.getIngredientWriteOff: Get Non-Manual Wastes

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/storage.getIngredientWriteOff'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);

```

> Response example:

```json
{
  "response":[
    {
      "write_off_id":"1518217",
      "transaction_id":"388684",
      "tr_product_id":"2125179",
      "storage_id":"1",
      "to_storage":"0",
      "ingredient_id":"936",
      "product_id":"934",
      "modificator_id":"0",
      "prepack_id":"0",
      "weight":"1.00000",
      "unit":"p",
      "cost":"0",
      "cost_netto":"0",
      "user_id":"1",
      "type":"1",
      "time":"1510668937861",
      "date":"2017-11-14 17:15:38",
      "reason":"",
      "product_name":"Fiscal Test",
      "name":"Demo"
    }
  ]
}
```

The method returns non-manual wastes

### HTTP request

`GET https://joinposter.com/api/storage.getIngredientWriteOff`

### GET parameters of the storage.getIngredientWriteOff request

Parameter | Description
--------- | -----------
dateFrom | An optional parameter, the sampling start date in the `Ymd` format, inclusive. The default date is a month ago.
dateTo | An optional parameter, the sampling end date in the `Ymd` format, inclusive. The default date is the current date.
storage_id | An optional parameter, the ID of the storage to return wastes. The default value is all storages.
ingredient_id | An optional parameter, the ID of the ingredient to return wastes for. The default value is all ingredients.

### The storage.getIngredientWriteOff response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an array, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
write_off_id | Waste ID
transaction_id | Transaction ID
storage_id | Waste storage ID
to_storage | Transfer storage ID
ingredient_id | Ingredient ID
product_id | Product ID
modificator_id | Modifier ID; if there is no modifier, it is 0
prepack_id | Semi-finished product ID
weight | Ingredient count
unit | Ingredient unit: kg—kilograms, p—pieces, l—liters
cost | The total waste amount for the ingredient in kopecks. If you need to know the food cost, divide `cost` by `weight`.
cost_netto | The total waste amount for the ingredient without VAT in kopecks. If you need to know the food cost, divide `cost` by `weight`.  Is returned if the 'Calculate cost and net profit' setting is enabled
user_id | Waiter ID
type | Operation type: 4—transfer, 1—waste, 2—manual waste
time | Waste date in the unixtimestamp format
date | Waste date
product_name | Product name
name | Waiter’s name
