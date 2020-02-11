## storage.getWaste: Manual Waste Data

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/storage.getWaste'
  . '?token=687409:4164553abf6a031302898da7800b59fb'
  . '&waste_id=1';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response": {
    "waste_id": 1,
    "total_sum": 2800,
    "total_sum_netto": 2333,
    "user_id": 1,
    "storage_id": 1,
    "date": "2017-04-26 14:30:02",
    "reason_id": 1,
    "reason_name": "Истек срок годности",
    "elements": [
      {
        "type": 8,
        "product_id": 8,
        "modificator_id": 2,
        "count": 1,
        "ingredients": [
          {
            "write_off_id": 118,
            "ingredient_id": 21,
            "product_id": 8,
            "modificator_id": 2,
            "prepack_id": 0,
            "weight": 1,
            "unit": "p",
            "cost": 800,
            "cost_netto": 667
          }
        ]
      },
      {
        "type": 3,
        "product_id": 4,
        "count": 1,
        "ingredients": [
          {
            "write_off_id": 121,
            "ingredient_id": 16,
            "product_id": 4,
            "modificator_id": 0,
            "prepack_id": 0,
            "weight": 1,
            "unit": "kg",
            "cost": 500,
            "cost_netto": 417
          },
          {
            "write_off_id": 122,
            "ingredient_id": 15,
            "product_id": 4,
            "modificator_id": 0,
            "prepack_id": 0,
            "weight": 1,
            "unit": "kg",
            "cost": 1500,
            "cost_netto": 1250
          }
        ]
      }
    ]
  }
}
```

The method returns the specific manual waste detailed data

### HTTP request

`GET https://joinposter.com/api/storage.getWaste`

### GET parameters of the storage.getWaste request

Parameter | Description
--------- | -----------
waste_id | Manual waste ID to return the detailed data to

### The storage.getWaste response parameters

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
elements | List of wasted entities.

Each element inside `elements` has the following parameters:

Parameter | Description
--------- | -----------
type | Wasted entity type: 1—product, 2—dish, 3—semi-finished product, 8—modifier, 10—ingredient
product_id | Product ID
modificator_id | Modifier ID
count | Wasted specific entities count
ingredients | Wasted ingredient array

Each element inside `ingredients` has the following parameters:

Parameter | Description
--------- | -----------
ingredient_id | Ingredient ID
write_off_id | Specific waste ID
prepack_id | Pack ID
product_id | Product ID
weight | The waste amount in kilograms, liters, or units
unit | unit
cost | The total waste amount for the ingredient in kopecks. If you need to know the food cost, divide `cost` by `weight`.
cost_netto | The total waste amount for the ingredient without VAT in kopecks. If you need to know the food cost, divide `cost` by `weight`. Is returned if the 'Calculate cost and net profit' setting is enabled
