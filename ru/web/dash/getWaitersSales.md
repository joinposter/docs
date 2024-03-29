## dash.getWaitersSales: Продажи по официантам

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/dash.getWaitersSales'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&dateFrom=20170901';

$data = sendRequest($url);
```

> Пример ответа:

```json 
{
  "response":[
    {
      "user_id":"1",
      "name":"Demo",
      "profit":"153707331",
      "profit_netto":"128089443",
      "revenue":"186224294",
      "clients":"1414",
      "middle_time":49364.020916667,
      "middle_invoice":1317.0034936351
    },
    {
      "user_id":"2",
      "name":"Максим",
      "profit":"147406757",
      "profit_netto":"122838964",
      "revenue":"179108697",
      "clients":"1314",
      "middle_time":58078.986483333,
      "middle_invoice":1363.0798858447
    },
    {
      "user_id":"6",
      "name":"Антон",
      "profit":"155127873",
      "profit_netto":"129273228",
      "revenue":"188413623",
      "clients":"1424",
      "middle_time":1.8170166666667,
      "middle_invoice":1323.129375
    }
  ]
}
```

Метод возвращет продажи по официантам

### HTTP запрос

`GET https://joinposter.com/api/dash.getWaitersSales`

### GET-параметры запроса dash.getWaitersSales

Параметр | Описание
-------- | --------
dateFrom | Опциональный параметр, дата начала выборки в формате `Ymd`, включает указанный день. По умолчанию дата месяц назад.
dateTo | Опциональный параметр, дата конца выборки в формате `Ymd`, включает указанный день. По умолчанию дата текущего дня.

### Параметры ответа dash.getWaitersSales

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит объект, внутри которого есть следующие параметры:

Параметр | Описание
-------- | --------
user_id | Id официанта
name | Имя официанта
revenue | Сумма выручки в копейках
profit | Прибыль в копейках
profit_netto | Прибыль без НДС в копейках. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
clients | Количество закрытых чеков
middle_invoice | Средний чек в гривнах
middle_time | Общее время, потраченное на обслуживание в минутах
worked_time | Отработанное время, официанта в минутах
