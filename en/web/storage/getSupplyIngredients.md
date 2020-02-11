## storage.getSupplyIngredients: Get the Supply Ingredients

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/storage.getSupplyIngredients'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&supply_id=46';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response":[
    {
      "ingredient_id":"66",
      "supply_ingredient_num":"3.00000",
      "supply_ingredient_sum":"15000",
      "supply_ingredient_sum_netto":"12500",
      "ingredient_name":"Шен Да Бай Ча-Дзень Гу",
      "ingredient_unit":"kg",
      "tax_id": 0
    },
    {
      "ingredient_id":"68",
      "supply_ingredient_num":"2.50000",
      "supply_ingredient_sum":"17500",
      "supply_ingredient_sum_netto":"14583",
      "ingredient_name":"Шен Мен Ку",
      "ingredient_unit":"kg",
      "tax_id": 0
    },
    {
      "ingredient_id":"67",
      "supply_ingredient_num":"130000.00000",
      "supply_ingredient_sum":"650000000",
      "supply_ingredient_sum_netto":"541666667",
      "ingredient_name":"Шен с горы У Лянь Шань-Дзень Гу",
      "ingredient_unit":"kg",
      "tax_id": 0
    },
    {
      "ingredient_id":"69",
      "supply_ingredient_num":"1400.00000",
      "supply_ingredient_sum":"16100000",
      "supply_ingredient_sum_netto":"13416667",
      "ingredient_name":"Шу Пуэр 20 лет",
      "ingredient_unit":"p",
      "tax_id": 0
    },
    {
      "ingredient_id":"76",
      "supply_ingredient_num":"30.00000",
      "supply_ingredient_sum":"390",
      "supply_ingredient_sum_netto":"325",
      "ingredient_name":"Яйца куринные",
      "ingredient_unit":"p",
      "tax_id": 0
    }
  ]
}
```

The method returns the supply ingredients

### HTTP request

`GET https://joinposter.com/api/storage.getSupplyIngredients`

### GET parameters of the storage.getSupplyIngredients request

Parameter | Description
--------- | -----------
supply_id | A mandatory parameter, the supply ID

### The storage.getSupplyIngredients response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an array, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
ingredient_id | Ingredient ID
supply_ingredient_num | Ingredient count
supply_ingredient_sum | Total amount of supply per ingredient in kopecks
supply_ingredient_sum_netto | Total amount of supply per ingredient without VAT in kopecks. Is returned if the 'Calculate cost and net profit' setting is enabled
ingredient_name | Ingredient name
ingredient_unit | Unit: kg—kg, p—pcs, l—l
tax_id | Tax ID
