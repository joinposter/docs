## finance.getCategories: Получить список категорий счетов

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/finance.getCategories'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Пример ответа:

```json
{
  "response":[
    {
      "category_id":"5",
      "name":"Зарплата",
      "parent_id":"0",
      "operations":"2",
      "action":"0",
      "delete":"0"
    },
    {
      "category_id":"2",
      "name":"Кассовые смены",
      "parent_id":"0",
      "operations":"3",
      "action":"11",
      "delete":"0"
    }
  ]
}
```

Метод получить список категорий по финансовым счетам

### HTTP запрос

`GET https://joinposter.com/api/finance.getCategories`

### Параметры ответа finance.getCategories

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит массив объектов, внутри каждого есть следующие параметры:

Параметр | Описание
-------- | --------
category_id | id категории
name | Название категории
parent_id | id подкатегории 
operation | Допустимые транзакции: 1 — доходы, 2 — расходы, 3 — доходы и расходы, 0 — не выбрано 
action | Тип категорий по действиям: 1 — переводы, 11 — кассовые смены, 12 — поставоки, 14 — актуализация, 0 — любой тип действия
