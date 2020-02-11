## finance.getAccounts: Получить счета

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/finance.getAccounts'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Пример ответа:

```json
{
  "response":[
    {
      "account_id":"1",
      "name":"Наличные в заведении",
      "currency_id":"2",
      "type":"3",
      "balance":"545643467264",
      "balance_start":"200000000",
      "percent_acquiring":"0.00",
      "currency_symbol":"<i class=\"icon-rouble\"><\/i>",
      "currency_code_iso":"RUB",
      "currency_code":"руб."
    },
    {
      "account_id":"2",
      "name":"Счет ИП",
      "currency_id":"2",
      "type":"1",
      "balance":"83086475682",
      "balance_start":"790000",
      "percent_acquiring":"0.00",
      "currency_symbol":"<i class=\"icon-rouble\"><\/i>",
      "currency_code_iso":"RUB",
      "currency_code":"руб."
    },
    {
      "account_id":"3",
      "name":"Сейф",
      "currency_id":"2",
      "type":"3",
      "balance":"56720000",
      "balance_start":"65000000",
      "percent_acquiring":"0.00",
      "currency_symbol":"<i class=\"icon-rouble\"><\/i>",
      "currency_code_iso":"RUB",
      "currency_code":"руб."
    }
  ]
}
```

Метод возвращает счета в разделе финансы

### HTTP запрос

`GET https://joinposter.com/api/finance.getAccounts`

### GET-параметры запроса finance.getAccounts

Параметр | Описание
-------- | --------
type | Тип счета: 1 — безналичный, 2 — банковская карта, 3 — наличные. По умолчанию все счета.

### Параметры ответа finance.getAccounts

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит массив объектов, внутри каждого есть следующие параметры:

Параметр | Описание
-------- | --------
account_id | id счета
name | Название счета
type | Тип счета: 1 — безналичный, 2 — банковская карта, 3 — наличные
balance | Баланс по счету в гривнах\рублях
balance_start | Начальный баланс в гривнах\рублях, остаток денег на счете на момент создания
percent_acquiring | Процент за эквайринг
currency_id | Id валюты в Poster: 1 — гривна, 2 — рубль, 3 — доллар, 4 — евро, 5 — тенге, 6 — лари, 7 — бат, 8 — armenia dram
currency_name | Название валюты
currency_code | Код валюты на терминале
currency_symbol | Unicode символ валюты, для рубля, драма и маната приходит HTML который на терминале отобразиться как иконка валюты
currency_code_iso | Цифровой код валюты по стандарту ISO 4217
