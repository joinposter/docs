## storage.getSupplyIngredients: Получить ингредиенты в поставке

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/storage.getSupplyIngredients'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&supply_id=46';

$data = sendRequest($url);
```

> Пример ответа:

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

Метод возвращает ингредиенты в поставке

### HTTP запрос

`GET https://joinposter.com/api/storage.getSupplyIngredients`

### GET-параметры запроса storage.getSupplyIngredients

Параметр | Описание
-------- | --------
supply_id | Обязательный параметр, id поставки

### Параметры ответа storage.getSupplyIngredients

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит массив, в каждом элементе которого есть следующие параметры:

Параметр | Описание
-------- | --------
ingredient_id | id ингредиента
supply_ingredient_num | Количество ингредиента
supply_ingredient_sum | Общая сумма поставки по ингредиенту в копейках
supply_ingredient_sum_netto | Общая сумма поставки по ингредиенту без НДС в копейках. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
ingredient_name | Название ингредиента
ingredient_unit | Единица измерения: kg — кг, p — шт, l — л
tax_id | Id налога
