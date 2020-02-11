## storage.getStorageLeftovers: Получить все остатки на складах

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/storage.getStorageLeftovers'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Пример ответа:

```json
{
  "response":[
    {
      "ingredient_id":"39",
      "ingredient_name":"Яблоки",
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
      "ingredient_name":"Яблочный",
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
      "ingredient_name":"Яйца куринные",
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

Метод возвращает остатки по складам

### HTTP запрос

`GET https://joinposter.com/api/storage.getStorageLeftovers`

### GET-параметры запроса storage.getStorageLeftovers

Параметр | Описание
-------- | --------
storage_id | Опциональный параметр, id склада по которому возвращать остатки. Если не указан, будут выданы по все складам.
type | Опциональный параметр, тип сущности по которой возвращать остатки: 1 — товар, 2 — производимая тех-карта, 3 — производимый полуфабрикат, ингредиент — 4, модификатор товара — 5. Если не указан, будут выданы по все сущностям. 
category_id | Опциональный параметр, id категории по которой получать ингредиенты. По умолчанию по всем категориям. 
zero_leftovers | Опциональный параметр, если `true`, метод возвращает нулевые остатки. По умолчанию, не возвращаются. 

### Параметры ответа storage.getStorageLeftovers

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит массив, в каждом элементе которого есть следующие параметры:

Параметр | Описание
-------- | --------
ingredient_id | id ингредиента
ingredient_name | Название ингредиента
ingredient_left | Общий остаток по всем складам
limit_value | Лимит на складе после привышения которого присылается оповещение 
ingredient_unit | Единица измерения: kg — кг, p — шт, l — л
ingredients_type | Тип объекта: ингредиент — 1, 2 — товар, модификатор товара
storage_ingredient_left | Остаток на складе, передается при применении параметра `storage_id`. Единицу измерения берет из параметра `ingredient_unit`
storage_ingredient_sum | Общая сумма товара на складе в копейках
storage_ingredient_sum_netto | Общая сумма товара на складе без НДС в копейках. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
prime_cost | Себестоимость ингредиента в копейках 
prime_cost_netto | Себестоимость ингредиента без НДС в копейках. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
hidden | Признак скрыт ли ингредиент: 1 — скрыт, 0 — нет 
