## storage.getStorageInventories: Получить архив инвентаризаций по складам

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/storage.getStorageInventories'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&storage_id=1';

$data = sendRequest($url);
```

> Пример ответа:

```json
{
  "response":[
    {
      "inventory_id":"3",
      "storage_id":"1",
      "date_start":"2015-08-12 19:07:08",
      "date_end":"2017-05-18 09:10:31",
      "date_set":"0000-00-00 00:00:00",
      "date_inventory":"2017-05-18 09:10:31",
      "sum":"871875648398",
      "sum_netto":"726563040332",
      "inventory_status":"1"
    },
    {
      "inventory_id":"2",
      "storage_id":"1",
      "date_start":"2015-02-05 13:10:26",
      "date_end":"2015-08-12 19:07:08",
      "date_set":"0000-00-00 00:00:00",
      "date_inventory":"0000-00-00 00:00:00",
      "sum":"104384",
      "sum_netto":"86987",
      "inventory_status":"1"
    },
    {
      "inventory_id":"1",
      "storage_id":"1",
      "date_start":"2013-08-09 16:30:13",
      "date_end":"2015-02-05 13:10:26",
      "date_set":"0000-00-00 00:00:00",
      "date_inventory":"0000-00-00 00:00:00",
      "sum":"-21236",
      "sum_netto":"-17697",
      "inventory_status":"1"
    }
  ]
}
```

Метод возвращает архив инвентаризаций по складам 

### HTTP запрос

`GET https://joinposter.com/api/storage.getStorageInventories`

### GET-параметры запроса storage.getStorageInventories

Параметр | Описание
-------- | --------
storage_id | Обязательный параметр, id склада по которому возвращать инвентаризации

### Параметры ответа storage.getStorageInventories

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит массив, в каждом элементе которого есть следующие параметры:

Параметр | Описание
-------- | --------
inventory_id | id инвентаризации
storage_id | id склада 
data_start | Дата начала инвентаризации 
data_end | Дата окончания инвентаризации
date_set | Дата проведения задним числом. Если инвентаризацию проводили задним числом то соответсвует `date_end`.
data_inventory | Реальная дата проведения инвентаризации
sum | Общая сума себестоимостей товаров инвентаризации в копейках
sum_netto | Общая сума себестоимостей товаров инвентаризации в копейках без НДС. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
inventory_status | Статус инвентаризации: 1 — проведенная, 0 — не проведенная
