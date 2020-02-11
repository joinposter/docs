## finance.getTransactions: Получить все транзакции 

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/finance.getTransactions'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&dateFrom=20170701'
 . '&dateTo=20170901';


$data = sendRequest($url);

```

> Пример ответа:

```json
{
  "response":[
    {
      "transaction_id":"538",
      "account_id":"1",
      "user_id":"1",
      "category_id":"7",
      "type":"0",
      "amount":"-8137663",
      "balance":"545516997964",
      "date":"2017-08-31 09:20:22",
      "recipient_type":"0",
      "recipient_id":"0",
      "binding_type":"15",
      "binding_id":"400",
      "comment":"Корректирующая транзакция",
      "delete":"0",
      "account_name":"Наличные в заведении",
      "currency_symbol":"<i class=\"icon-rouble\"><\/i>",
      "category_name":"Actualization"
    },
    {
      "transaction_id":"536",
      "account_id":"1",
      "user_id":"1",
      "category_id":"2",
      "type":"1",
      "amount":"8148663",
      "balance":"545525135627",
      "date":"2017-08-31 09:20:21",
      "recipient_type":"0",
      "recipient_id":"0",
      "binding_type":"11",
      "binding_id":"400",
      "comment":"Закрытие наличной кассы",
      "delete":"0",
      "account_name":"Наличные в заведении",
      "currency_symbol":"<i class=\"icon-rouble\"><\/i>",
      "category_name":"Cash register shifts"
    }
  ]
}
```

Метод возвращает все транзакции 

### HTTP запрос

`GET https://joinposter.com/api/finance.getTransactions`

### GET-параметры запроса finance.getTransactions

Параметр | Описание
-------- | --------
account_id | Опциональный параметр, id счета, по умолчанию по всем счетам
category_id | Опциональный параметр, id категории, по умолчанию по всем категориям
dateFrom | Обязательный параметр, дата начала выборки в формате `Ymd`, включительно. По умолчанию дата месяц назад.
dateTo | Опциональный параметр, дата конца выборки в формате `Ymd`, включительно. По умолчанию дата текущего дня.
pretty | Опциональный параметр, возвращать данные в человекочитаемом формате. Все системные транзакии будут сведены к приходным или расходным транзакциям.

### Параметры ответа finance.getTransactions

Параметр | Описание
-------- | --------
response | Массив транзакций

Внутри параметра `response` лежит массив объектов, в каждом элементе которого есть следующие параметры:

Параметр | Описание
-------- | -------- 
transaction_id | id транзакции 
account_id | id счета 
user_id | id официанта 
category_id | id категории, по умолчанию по всем категориям
type | Тип транзакции: 0 — расход, 1 — доход
amount | Сумма транзакции в копейках
balance | Баланс на счете в копейках
date | Дата проведения транзакции
recipient_type | Тип принимающей сущности: 1 — перевод, 12 — поставщик
recipient_id | id принимающей сущности
binding_type | Тип соответствующей сущности: 1 — перевод, 12 — закрытие смены, 13 — поставка, 14 — транзакции кассовой смены
binding_id | id соответствующей сущности
comment | Комментарий
delete | Удалена ли транзакция: 0  — транзакция не удалена, 1 — транзакция удалена
account_name | Название счета
category_nam | Название категории
currency_symbol | Unicode символ валюты, для рубля, драма и маната приходит HTML который на терминале отобразиться как иконка валюты
