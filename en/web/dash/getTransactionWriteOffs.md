## dash.getTransactionWriteOffs: Order Wastes

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/dash.getTransactionWriteoffs'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&transaction_id=388678';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response":[
    {
      "write_off_id":"1518199",
      "tr_product_id":"2125168",
      "storage_id":"1",
      "ingredient_id":"833",
      "product_id":"168",
      "modificator_id":"0",
      "prepack_id":"0",
      "weight":"1.00000",
      "unit":"p",
      "cost":22.13,
      "cost_netto":18.44,
      "time":"1507703520358"
    },
    {
      "write_off_id":"1518200",
      "tr_product_id":"2125169",
      "storage_id":"1",
      "ingredient_id":"85",
      "product_id":"169",
      "modificator_id":"0",
      "prepack_id":"0",
      "weight":0.04,
      "unit":"l",
      "cost":1.24,
      "cost_netto":1.03,
      "time":"1507703520358"
    },
    {
      "write_off_id":"1518201",
      "tr_product_id":"2125169",
      "storage_id":"1",
      "ingredient_id":"78",
      "product_id":"169",
      "modificator_id":"0",
      "prepack_id":"0",
      "weight":0.059,
      "unit":"kg",
      "cost":2.12,
      "cost_netto":1.77,
      "time":"1507703520358"
    },
    {
      "write_off_id":"1518202",
      "tr_product_id":"2125169",
      "storage_id":"1",
      "ingredient_id":"84",
      "product_id":"169",
      "modificator_id":"0",
      "prepack_id":"0",
      "weight":0.128,
      "unit":"kg",
      "cost":2.68,
      "cost_netto":2.23,
      "time":"1507703520358"
    },
    {
      "write_off_id":"1518203",
      "tr_product_id":"2125169",
      "storage_id":"1",
      "ingredient_id":"86",
      "product_id":"169",
      "modificator_id":"0",
      "prepack_id":"0",
      "weight":0.608,
      "unit":"kg",
      "cost":37.35,
      "cost_netto":31.13,
      "time":"1507703520358"
    },
    {
      "write_off_id":"1518204",
      "tr_product_id":"2125170",
      "storage_id":"1",
      "ingredient_id":"97",
      "product_id":"908",
      "modificator_id":"68",
      "prepack_id":"918",
      "weight":0.15,
      "unit":"kg",
      "cost":0.43,
      "cost_netto":0.36,
      "time":"1507703520358"
    }
  ]
}
```

The method receives all order wastes

### HTTP request

`GET https://joinposter.com/api/dash.getTransactionWriteoffs`

### GET parameters of the dash.getTransactionWriteOffs request

Parameter | Description
--------- | -----------
transaction_id | A mandatory parameter, the transaction ID (order number)

### Parameters of the dash.getTransactionWriteOffs response

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
write_off_id | Waste ID
transaction_id | Transaction (order) ID
storage_id | Waste storage ID
to_storage | The ID of the storage the product has been transferred to; transmitted if there has been a transference
ingredient_id | Ingredient ID
product_id | Product ID
modificator_id | Modifier ID; if there is no modifier, it is 0
prepack_id | Semi-finished product ID
weight | Count
unit | Ingredient unit: kg—kilograms, p—pieces, l—liters
cost | The ingredient cost multiplied by the count in hryvnias/rubles
cost_netto | The ingredient cost without VAT multiplied by the count in hryvnias/rubles. Is returned if the 'Calculate cost and net profit' setting is enabled
user_id | Waiter ID
type | Operation type: 4—transfer, 1—waste, 2—manual waste
time | Waste date in the unixtimestamp format
reason | Waste reason
