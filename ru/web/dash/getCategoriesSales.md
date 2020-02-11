## dash.getCategoriesSales: Продажи по категориям

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/dash.getCategoriesSales'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&dateFrom=20170920'
 . '&dateTo=20170922';

$data = sendRequest($url);
```

> Пример ответа:

```json
{
  "response":[
    {
      "revenue":"38568300",
      "profit":"36307114",
      "profit_netto":"30255928",
      "count":"1173",
      "category_name":"Вторые блюда",
      "category_id":"33"
    },
    {
      "revenue":"36970440",
      "profit":"21885184",
      "profit_netto":"18237653",
      "count":"863",
      "category_name":"Главный экран",
      "category_id":0
    },
    {
      "revenue":"34474000",
      "profit":"31377831",
      "profit_netto":"26148193",
      "count":"830",
      "category_name":"Салаты",
      "category_id":"31"
    },
    {
      "revenue":"33876200",
      "profit":"31379225",
      "profit_netto":"26149354",
      "count":"905",
      "category_name":"Торты",
      "category_id":"37"
    },
    {
      "revenue":"22781920",
      "profit":"18568329",
      "profit_netto":"15473608",
      "count":"1173",
      "category_name":"Кофе",
      "category_id":"10"
    }
  ]
}
```

Метод возвращает продажи по категориям 

### HTTP запрос

`GET https://joinposter.com/api/dash.getCategoriesSales`

### GET-параметры запроса dash.getCategoriesSales

Параметр | Описание
-------- | --------
dateFrom | Дата начала для выборки в формате `Ymd`. Если не указана, начальная дата считается на месяц позже.
dateTo | Дата конца для выборки в формате `Ymd`. Если не указана, конечная дата считается текущей.
spot_id | id заведения, если не указана, будут выданы по всем заведениям 

### Параметры ответа dash.getCategoriesSales

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит массив объектов. Внутри каждого объекта есть следующие параметры:

Параметр | Описание
-------- | --------
revenue | Сумма выручки в копейках
profit | Сумма прибыли в копейках
profit_netto | Сумма прибыли без НДС в копейках. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
count | Количество продаж
category_name | Название категории
category_id | id категории
