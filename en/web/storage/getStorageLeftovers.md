## storage.getStorageLeftovers: Get all the Storage Inventories

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/storage.getStorageLeftovers'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response":[
    {
      "ingredient_id":"39",
      "ingredient_name":"Apples",
      "ingredient_left":"3143.00000",
      "limit_value":"0",
      "ingredient_unit":"p",
      "ingredients_type":"2",
      "storage_ingredient_sum":"4591923",
      "storage_ingredient_sum_netto":"3826603",
      "prime_cost":1461,
      "prime_cost_netto":1218,
      "hidden":"0"
    },
    {
      "ingredient_id":"11",
      "ingredient_name":"Apple",
      "ingredient_left":"-908.00000",
      "limit_value":"0",
      "ingredient_unit":"p",
      "ingredients_type":"2",
      "storage_ingredient_sum":"0",
      "storage_ingredient_sum_netto":"0",
      "prime_cost":1299,
      "prime_cost_netto":1083,
      "hidden":"0"
    },
    {
      "ingredient_id":"76",
      "ingredient_name":"Eggs",
      "ingredient_left":"-1678.00000",
      "limit_value":"0",
      "ingredient_unit":"p",
      "ingredients_type":"1",
      "storage_ingredient_sum":"0",
      "storage_ingredient_sum_netto":"0",
      "prime_cost":174,
      "prime_cost_netto":145,
      "hidden":"0"
    }
  ]
}
```

The method returns the storage inventories

### HTTP request

`GET https://joinposter.com/api/storage.getStorageLeftovers`

### GET parameters of the storage.getStorageLeftovers request

Parameter | Description
--------- | -----------
storage_id | An optional parameter, the ID of the storage to return inventories to. If not specified, they will be displayed for all the storages.
type | An optional parameter, the type of entity to return the inventories by: 1—product, 2—manufactured dish, 3—produced semi-finished product, 4—ingredient, 5—product modifier. If not specified, they will be displayed for all entities.
category_id | An optional parameter, the category ID to receive ingredients by. The default value is all categories.
zero_leftovers | An optional parameter; if `true`, the method returns zero inventories. By default, they are not returned.

### The storage.getStorageLeftovers response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an array, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
ingredient_id | Ingredient ID
ingredient_name | Ingredient name
ingredient_left | Total inventory for all storages
limit_value | Low stock alert threshold the exceeding of which is notified of
ingredient_unit | Unit: kg—kg, p—pcs, l—l
ingredients_type | Object type: 1—ingredient, 2—product, product modifier
storage_ingredient_left | Storage balance is transferred when the `storage_id` parameter is applied. The measurement unit is taken from the `ingredient_unit` parameter
storage_ingredient_sum | Total product amount in storage in kopecks
storage_ingredient_sum_netto | Total product amount in storage without VAT in kopecks. Is returned if the 'Calculate cost and net profit' setting is enabled
prime_cost | Ingredient food cost in kopecks
prime_cost_netto | Ingredient food cost without VAT in kopecks. Is returned if the 'Calculate cost and net profit' setting is enabled
hidden | The status of the ingredient being hidden: 1—hidden, 0—not hidden
