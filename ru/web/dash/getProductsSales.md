## dash.getProductsSales: Продажи по товарам

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/dash.getProductsSales'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Пример ответа:

```json
{
  "response":[
    {
      "product_name":"Стейк из сёмги",
      "modificator_name":null,
      "product_id":"168",
      "modification_id":"0",
      "delete":"0",
      "left":"43",
      "right":"44",
      "category_id":"33",
      "count":"171.0000",
      "weight_flag":"0",
      "payed_sum":"7650000",
      "product_sum":"7695000",
      "bonus_sum":"0",
      "cert_sum":"45000",
      "product_profit":"7199716",
      "product_profit_netto":"5999763",
      "tax_sum":"72000",
      "vat_sum":"0",
      "unit":"p",
      "discount":45000
    },
    {
      "product_name":"Речная форель в фольге",
      "modificator_name":null,
      "product_id":"169",
      "modification_id":"0",
      "delete":"0",
      "left":"43",
      "right":"44",
      "category_id":"33",
      "count":"168.0000",
      "weight_flag":"0",
      "payed_sum":"9185000",
      "product_sum":"9240000",
      "bonus_sum":"0",
      "cert_sum":"55000",
      "product_profit":"8367880",
      "product_profit_netto":"6973233",
      "tax_sum":"88000",
      "vat_sum":"0",
      "unit":"p",
      "discount":55000
    }
  ]
}
```

Метод возвращает продажи по товарам 

### HTTP запрос

`GET https://joinposter.com/api/dash.getProductsSales`

### GET-параметры запроса dash.getProductsSales

Параметр | Описание
-------- | --------
spot_id | Опциональный параметр, Id заведения по которому возвращать статистику
date_from | Опциональный параметр, дата начала выборки в формате `Ymd`, включительно. По умолчанию дата месяц назад.
date_to | Опциональный параметр, дата конца выборки в формате `Ymd`, включительно. По умолчанию дата текущего дня.

### Параметры ответа dash.getProductsSales

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит массив объектов. Внутри каждого объекта есть следующие параметры:

Параметр | Описание
-------- | --------
product_name | Название товара 
product_id | id товара
modification_id | id модификатора, 0 если товар без модификатора
modification_name | Название модификатора, `null` если товар без модификатора
category_id | Id категории товара
left | Id категории слева
right | Id категории справа
price | Стоимость товара 
count | Количество проданого товара
weight_flag | Признак весового товара, 0 — не весовой, 1 — если весовой
payed_sum | Сумма уплаченная "живыми деньгами c учетом скидки", равна `payed_cash` + `payed_card`
product_sum | Цена в копейках
product_profit | Прибыль в копейках
product_profit_netto | Прибыль без НДС в копейках. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
discount | Сумма скидка в копейках 
delete | Признак удален ли товар: 0 — не удален, 1 — удален
