## storage.getReportMovement: Отчет по движению

>  Пример запроса:

```php
<?
$url = 'https://joinposter.com/api/storage.getReportMovement'
  . '?token=687409:4164553abf6a031302898da7800b59fb'
  . '&dateFrom=20170101'
  . '&dateTo=20180101'
  . '&storage_id=1'
  . '&type=2';

$data = sendRequest($url);
```

> Пример ответа:

```json
{
   "response":[
      {
         "ingredient_id":"332",
         "ingredient_name":"Borjome",
         "cost_start":13.63,
         "cost_end":13.63,
         "start":14,
         "income":0,
         "write_offs":0,
         "end":14
      },
      {
         "ingredient_id":"260",
         "ingredient_name":"Sprite",
         "cost_start":8.39,
         "cost_end":8.39,
         "start":2,
         "income":0,
         "write_offs":0,
         "end":2
      }
   ]
}
```

Запрос на получение отчета по движению ингредиентов

### HTTP запрос

`GET https://joinposter.com/api/storage.getReportMovement`


### GET-параметры запроса storage.getReportMovement

Параметр | Описание
-------- | --------
dateFrom | Опциональный параметр, дата начала выборки в формате `Ymd`, включительно. По умолчанию дата месяц назад.
dateTo | Опциональный параметр, дата конца выборки в формате `Ymd`, включительно. По умолчанию дата текущего дня.
storage_id | Опциональный параметр, обозначает id склада
type | Опциональный параметр, тип ингредиентов, по которым нужно получить ответ: 1 — ингредиенты, 2 — товары, 3 — модификации товаров, 4 - тех. карты, 5 - полуфабрикаты.

### Параметры ответа storage.getReportMovement

Параметр | Описание
-------- | ---------
ingredient_id | Id ингредиента
ingredient_name | Название ингредиента
cost_start | Средняя себестоимость ингредиента на дату начала выборки в рублях\гривнах
cost_end | Средняя себестоимость ингредиета на дату окончания выборки в рублях\гривних 
start | Остаток ингредиента на дату начала выборки
income | Поступления ингредиента
write_offs | Расход ингредиента
end | Остаток ингредиента на дату конца выборки
