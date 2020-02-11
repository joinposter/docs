## storage.getWastes: Список ручных списаний

>  Пример запроса:

```php
<?
$url = 'https://joinposter.com/api/storage.getWastes'
  . '?token=687409:4164553abf6a031302898da7800b59fb'
  . '&dateFrom=20170101'
  . '&dateTo=20180101'
  . '&1c=true';

$data = sendRequest($url);
```

> Пример ответа:

```json
{
  "response": [
    {
      "waste_id": 1,
      "total_sum": 2800,
      "total_sum_netto": 2333,
      "user_id": 1,
      "storage_id": 1,
      "date": "2017-04-26 14:30:02",
      "reason_id": 0,
      "reason_name": null,
      "delete": 0
    },
    {
      "waste_id": 2,
      "total_sum": 791,
      "total_sum_netto": 659,
      "user_id": 1,
      "storage_id": 1,
      "date": "2017-04-26 15:21:12",
      "reason_id": 1,
      "reason_name": "Истек срок годности",
      "delete": 1
    }
  ]
}
```

Запрос на получение списка всех ручных списаний.

### HTTP запрос

`GET https://joinposter.com/api/storage.getWastes`

### GET-параметры запроса storage.getWastes

Параметр | Описание
-------- | --------
dateFrom | Опциональный параметр. Дата начала выборки (Ymd). По умолчанию дата месяц назад.
dateTo | Опциональный параметр. Дата конца выборки (Ymd). По умолчанию дата текущего дня.
1с_id | Опциональный параметр. Позволяет возвращать ручные списания с учётом удалённых (вернёт флаг delete). В качестве значения необходимо указать true.

### Параметры ответа storage.getWastes

Параметр | Описание
-------- | ---------
waste_id | id ручного списания
total_sum | Общая сумма списания
total_sum_netto | Общая сумма списания без НДС. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
user_id | id пользователя, который произвёл списание
storage_id | id склада с которого было произведено списание
date | Дата списания
reason_id | id причины списания
reason_name | Причина списания
delete | Признак что списание удалено: 1 — удалено, 0 — нет
