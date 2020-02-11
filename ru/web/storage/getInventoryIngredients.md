## storage.getInventoryIngredients: Получить инвентаризацию по ингредиентам 

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/storage.getInventoryIngredients'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&storage_id=1';

$data = sendRequest($url);
```

> Пример ответа:

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

Метод возвращает инвентаризацию по ингредиентам 

### HTTP запрос

`GET https://joinposter.com/api/storage.getInventoryIngredients`

### GET-параметры запроса storage.getInventoryIngredients

Параметр | Описание
-------- | --------
storage_id | id склада, если `inventory_id` не указан то обязательный параметр
inventory_id | id инвентаризации, если `storage_id` не указан то обязательный параметр

### Параметры ответа storage.getInventoryIngredients

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит объект, внутри которого есть следующие параметры:

Параметр | Описание
-------- | --------
ingredients | Массив ингредиентов
manufactures | Массив производств
prepacks | Массив тех. карт, и полуфабрикатов

Массив `ingredients` содержит объекты со следующими параметрами:

Параметр | Описание
-------- | --------
item_id | id ингредиента
item | Название ингредиента
startrest | Начальный остаток
startrestcurrency | Начальный остаток в гривнах\рублях 
startrestcurrency_netto | Начальный остаток в гривнах\рублях без НДС. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
income | Количество приходов на склад по данному ингредиенту, учитывая поставки и перемещения
charges | Количество расходов по данному ингредиенту, учитывая списания, производства, продажи и перемещения
writeoff | Списанное количество  
writeoffcurrency | Списано в гривнах\рублях
writeoffcurrency_netto | Списано в гривнах\рублях без НДС. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
estimatedrest | Плановый остаток
primecost | Себестоимость в гривнах\рублях
primecost_netto | Себестоимость в гривнах\рублях без НДС. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
factrest | Фактический остаток
fact_rest_in_prepack | Фактический остаток в блюдах и полуфабрикатах
fact_rest_in_sum | Сумма фактических остатков
difference | Разница в кол-ве между плановым и фактическим остатком
diffcurrency | Разница в гривнах\рублях. `difference` * `primecost`
diffcurrency_netto | Разница в гривнах\рублях без НДС. `difference` * `primecost`. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
partial_write_off | Признак что штучный ингредиент можно списывать как дробный: 1 — можно списывать, 0 — нет
unit | Единица измерения (шт/кг/л)
db_unit | Единица измерения ингредиента: kg — килограммы, p — штуки, l — литры

Массив `manufactures` содержит объекты со следующими параметрами:

Параметр | Описание
-------- | --------
item_id | id производства
item | Название производства
startrest | Начальный остаток в кол-ве
startrestcurrency | Начальный остаток в гривнах\рублях 
startrestcurrency_netto | Начальный остаток в гривнах\рублях без НДС. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
income | Количество приходов на склад по данному ингредиенту, учитывая поставки и перемещения
charges | Количество расходов по данному ингредиенту, учитывая списания, производства, продажи и перемещения
writeoff | Списанное количество
writeoffcurrency | Сумма списания в гривнах\рублях  
writeoffcurrency_netto | Сумма списания в гривнах\рублях без НДС. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
estimatedrest | Плановый остаток
primecost | Себестоимость в гривнах\рублях
primecost_netto | Себестоимость в гривнах\рублях без НДС. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
factrest | Фактический остаток  
fact_rest_in_prepack | Фактический остаток в блюдах и полуфабрикатах
fact_rest_in_sum | Сумма в гривнах\рублях фактических остатков. Разница между фактическим и плановым остатком умноженная на себестоимость.
difference | Разница в кол-ве между плановым и фактическим остатком
diffcurrency | Разница в гривнах\рублях. `difference` * `primecost`
diffcurrency_netto | Разница в гривнах\рублях без НДС. `difference` * `primecost`. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
unit | Единица измерения (шт/кг/л)
db_unit | Единица измерения ингредиента: kg — килограммы, p — штуки, l — литры

Массив `prepacks` содержит объекты со следующими параметрами:

Параметр | Описание
-------- | --------
product_id | id тех. карты или полуфабриката
product_name | Название тех. карты или полуфабриката
count | Количество списанное в шт или кг
type | Тип товара: 1 — полуфабрикат, 2 — тех. карта
cost | Сумма списаний в гривнах\рублях
cost_netto | Сумма списаний в гривнах\рублях без НДС. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
weight_flag | Признак весовой тех. карты: 1 — весовая, 0 — нет
factrest | Фактический остаток 
