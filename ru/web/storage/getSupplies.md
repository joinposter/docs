## storage.getSupplies: Получить все поставки

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/storage.getSupplies'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Пример ответа:

```json
{
  "response":[
    {
      "supply_id":"48",
      "storage_id":"1",
      "supplier_id":"1",
      "date":"2017-11-17 08:09:33",
      "supply_sum":"1800",
      "supply_sum_netto":"1500",
      "supply_comment":"",
      "storage_name":"Склад Кухня",
      "supplier_name":"Закупщик",
      "delete":"1",
      "account_id":null
    },
    {
      "supply_id":"47",
      "storage_id":"1",
      "supplier_id":"1",
      "date":"2017-05-18 09:11:00",
      "supply_sum":"300000",
      "supply_sum_netto":"250000",
      "supply_comment":"",
      "storage_name":"Склад Кухня",
      "supplier_name":"Закупщик",
      "delete":"0",
      "account_id":null
    },
    {
      "supply_id":"46",
      "storage_id":"1",
      "supplier_id":"1",
      "date":"2017-05-18 09:07:00",
      "supply_sum":"669882890",
      "supply_sum_netto":"558235742",
      "supply_comment":"",
      "storage_name":"Склад Кухня",
      "supplier_name":"Закупщик",
      "delete":"0",
      "account_id":null
    }
  ]
}
```

Метод возвращает все поставки  

### HTTP запрос

`GET https://joinposter.com/api/storage.getSupplies`

### GET-параметры запроса storage.getSupplies

Параметр | Описание
-------- | --------
dateFrom | Опциональный параметр, дата начала выборки в формате `Ymd`, включительно. По умолчанию дата месяц назад.
dateTo | Опциональный параметр, дата конца выборки в формате `Ymd`, включительно. По умолчанию дата текущего дня.
limit | Опциональный параметр, количество поставок, которое необходимо получить. Если используется `dateFrom` и `dateTo` то этот параметр игнорируется. 
offset | Опциональный параметр, сколько записей необходимо пропустить от начала списка. По умолчанию, будут выданы все поставки.  Если используется `dateFrom` и `dateTo` то этот параметр игнорируется.


### Параметры ответа storage.getSupplies

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит массив, в каждом элементе которого есть следующие параметры:

Параметр | Описание
-------- | --------
supply_id | id поставки
storage_id | id склада на который поставляли
supplier_id | id поставщика
date | Дата поставки
account_id | id финансового счёта с которого списали поставку
supply_sum | Сумма поставки в копейках
supply_sum_netto | Сумма поставки без НДС в копейках. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
supply_comment | Комментарий
storage_name | Название склада
supplier_name | Имя поставщика
delete | Признак удалена ли поставка: 1 — удалена, 0 — нет
