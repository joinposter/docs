## storage.getMove: Get the Transfer Content

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/storage.getMove'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&move_id=2';

$data = sendRequest($url);

```

> Response example:

```json
{
  "response":[
    {
      "moving_id":2,
      "date":"2016-10-30 12:40:00",
      "from_storage":1,
      "from_storage_name":"Склад Кухня",
      "to_storage":2,
      "to_storage_name":"Склад Бар",
      "user_id":7,
      "user_name":"Poster Root",
      "sum":59.31,
      "sum_netto":49.43,
      "ingredients":[
        {
          "link_id":2,
          "ingredient_id":12,
          "product_id":142,
          "ingredient_num":10,
          "ingredient_sum":7.08,
          "ingredient_sum_netto":5.90,
          "type":1,
          "write_off_id":1216696,
          "packing_id":1
        },
        {
          "link_id":3,
          "ingredient_id":91,
          "ingredient_num":1,
          "ingredient_sum":52.23,
          "ingredient_sum_netto":43.53,
          "type":10,
          "write_off_id":1216697,
          "packing_id":2
        }
      ]
    }
  ]
}
```

The method returns the transfer content, including ingredients and products

### HTTP request

`GET https://joinposter.com/api/storage.getMove`

### GET parameters of the storage.getMove request

Parameter | Description
--------- | -----------
move_id | A mandatory parameter, the transfer ID
timezone | An optional parameter; if it equals `client`, the date is returned in the account time zone.

### The storage.getMove response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

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
ingredients | List of ingredients being transferred

Inside the `ingredients` parameter, there is an array of objects with the following parameters inside each of them:

Parameter | Description
--------- | -----------
ingredient_id | Ingredient ID
product_id | Product ID if it is a product, a modifier, a dish, or a semi-finished product
modificator_id | Modifier ID if it is a modifier
ingredient_num | Ingredient count
ingredient_sum | The transferred ingredient cost in hryvnias/rubles
ingredient_sum_netto | The transferred ingredient cost without VAT in hryvnias/rubles. Is returned if the 'Calculate cost and net profit' setting is enabled
type | Ingredient type: 1—product, 10—ingredient, 8—product modifier, 2—manufactured dish, 3—manufactured semi-finished product
packing_id | Pack ID

