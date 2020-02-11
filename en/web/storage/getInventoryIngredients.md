## storage.getInventoryIngredients: Get an Ingredient Inventory Check

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/storage.getInventoryIngredients'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&storage_id=1';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response":{
    "ingredients":{
      "115":{
        "item_id":"11",
        "item":"Яблочный",
        "startrest":655,
        "startrestcurrency":8508.45,
        "startrestcurrency_netto":7090.38,
        "income":0,
        "charges":1563,
        "writeoff":0,
        "writeoffcurrency":0,
        "writeoffcurrency_netto":0,
        "estimatedrest":-908,
        "primecost":12.99,
        "primecost_netto":10.83,
        "factrest":"''",
        "fact_rest_in_prepack":"''",
        "fact_rest_sum":"''",
        "difference":"''",
        "diffcurrency":"''",
        "diffcurrency_netto":"''",
        "partial_write_off":"0",
        "unit":"pcs",
        "db_unit":"p"
      },
      "116":{
        "item_id":"76",
        "item":"Яйца куринные (ing)",
        "startrest":21,
        "startrestcurrency":36.54,
        "startrestcurrency_netto":30.45,
        "income":0,
        "charges":1699,
        "writeoff":0,
        "writeoffcurrency":0,
        "writeoffcurrency_netto":0,
        "estimatedrest":-1678,
        "primecost":1.74,
        "primecost_netto":1.45,
        "factrest":"''",
        "fact_rest_in_prepack":"''",
        "fact_rest_sum":"''",
        "difference":"''",
        "diffcurrency":"''",
        "diffcurrency_netto":"''",
        "partial_write_off":"0",
        "unit":"pcs",
        "db_unit":"p"
      }
    },
    "manufactures":[

    ],
    "prepacks":{      
      "930":{
        "product_id":"930",
        "product_name":"Кальян с сюрпризом",
        "type":"2",
        "weight_flag":"0",
        "delete":"0",
        "factrest":0,
        "count":0,
        "cost":0,
        "cost_netto":0,
        "saved":0
      },
      "931":{
        "product_id":"931",
        "product_name":"Маринованные грибы",
        "type":"1",
        "weight_flag":"0",
        "delete":"0",
        "factrest":0,
        "count":0,
        "cost":0,
        "cost_netto":0,
        "saved":0
      }
    }
  }
}
```

The method returns an ingredient inventory check

### HTTP request

`GET https://joinposter.com/api/storage.getInventoryIngredients`

### GET parameters of the storage.getInventoryIngredients request

Parameter | Description
--------- | -----------
storage_id | Storage ID; if `inventory_id` is not specified, it’s a mandatory parameter
inventory_id | Inventory check ID; if `storage_id` is not specified, it’s a mandatory parameter

### The storage.getInventoryIngredients response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
ingredients | Ingredient array
manufactures | Manufacture array
prepacks | An array of dishes and semi-finished products

The `ingredients` array contains objects with the following parameters:

Parameter | Description
--------- | -----------
item_id | Ingredient ID
item | Ingredient name
startrest | Initial inventory
startrestcurrency | Initial inventory in hryvnias/rubles
startrestcurrency_netto | Initial inventory without VAT in hryvnias/rubles. Is returned if the 'Calculate cost and net profit' setting is enabled
income | The amount of storage incomes for the ingredient, considering the supplies and transfers
charset | The amount of expenditure for the ingredient, considering the wastes, manufacture, sales, and transfers
writeoff | Wasted amount
writeoffcurrency | Wastes in hryvnias/rubles
writeoffcurrency_netto | Wastes without VAT in hryvnias/rubles. Is returned if the 'Calculate cost and net profit' setting is enabled
estimatedrest | Estimated inventory
primecost | Food cost in hryvnias/rubles
primecost_netto | Food cost without VAT in hryvnias/rubles. Is returned if the 'Calculate cost and net profit' setting is enabled
factrest | Actual inventory
fact_rest_in_prepack | The actual inventory of dishes and semi-finished products
fact_rest_in_sum | Actual inventory amount
difference | The difference in number between the estimated and actual inventory
diffcurrency | The difference in hryvnias/rubles. `difference` * `primecost`
diffcurrency_netto | The difference without VAT in hryvnias/rubles. `difference` * `primecost`. Is returned if the 'Calculate cost and net profit' setting is enabled
partial_write_off | The status of an ingredient sold by the piece being allowed to be wasted as the one sold by fractions: 1—allowed, 0—not allowed
unit | Unit (pcs/kg/l)
db_unit | Ingredient unit: kg—kilograms, p—pieces, l—liters

The `manufactures` array contains objects with the following parameters:

Parameter | Description
--------- | -----------
item_id | Manufacture ID
item | Manufacture name
startrest | Initial inventory in the amount
startrestcurrency | Initial inventory in hryvnias/rubles
startrestcurrency_netto | Initial inventory without VAT in hryvnias/rubles. Is returned if the 'Calculate cost and net profit' setting is enabled
income | The amount of storage incomes for the ingredient, considering the supplies and transfers
charset | The amount of expenditure for the ingredient, considering the wastes, manufacture, sales, and transfers
writeoff | Wasted amount
writeoffcurrency | The waste amount in hryvnias/rubles
writeoffcurrency_netto | Wastes without VAT in hryvnias/rubles. Is returned if the 'Calculate cost and net profit' setting is enabled
estimatedrest | Estimated inventory
primecost | Food cost in hryvnias/rubles
primecost_netto | Food cost without VAT in hryvnias/rubles. Is returned if the 'Calculate cost and net profit' setting is enabled
factrest | Actual inventory
fact_rest_in_prepack | The actual inventory of dishes and semi-finished products
fact_rest_in_sum | The actual inventory amount in hryvnias/rubles. The difference between the actual and estimated inventory multiplied by the food cost.
difference | The difference in number between the estimated and actual inventory
diffcurrency | The difference in hryvnias/rubles. `difference` * `primecost`
diffcurrency_netto | The difference without VAT in hryvnias/rubles. `difference` * `primecost`. Is returned if the 'Calculate cost and net profit' setting is enabled
unit | Unit (pcs/kg/l)
db_unit | Ingredient unit: kg—kilograms, p—pieces, l—liters

The `prepacks` array contains objects with the following parameters:

Parameter | Description
--------- | -----------
product_id | The ID of a dish or a semi-finished product
product_name | The name of a dish or a semi-finished product
count | Wasted amount in pcs or kg
type | Product type: 1—semi-finished product, 2—dish
cost | The waste amount in hryvnias/rubles
cost_netto | The waste amount without VAT in hryvnias/rubles. Is returned if the 'Calculate cost and net profit' setting is enabled
weight_flag | The status of a dish sold by weight: 1—sold by weight, 0—not sold by weight
factrest | Actual inventory
