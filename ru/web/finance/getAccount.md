## finance.getAccount: Свойства счета

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/finance.getAccount'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&account_id=3';

$data = sendRequest($url);
```

> Пример ответа:

```json
{  
   "response":{  
      "account_id":"3",
      "name":"Сейф",
      "currency_id":"3",
      "type":"1",
      "balance":"56720000",
      "balance_start":"0",
      "percent_acquiring":"0.00",
      "currency_symbol":"$",
      "currency_code_iso":"USD",
      "currency_code":"usd"
   }
}
```

Метод возвращает свойства счета в разделе финансы

### HTTP запрос

`GET https://joinposter.com/api/finance.getAccount`

### GET-параметры запроса finance.getAccount

Параметр | Описание
-------- | --------
type | Тип счета: 1 — безналичный, 2 — банковская карта, 3 — наличные. По умолчанию все счета.
account_id | Обязательный параметр, id счета

### Параметры ответа finance.getAccount

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит объект, внутри которого есть следующие параметры:

Параметр | Описание
-------- | --------
account_id | Id счета
name | Название счета
type | Тип счета: 1 — безналичный, 2 — банковская карта, 3 — наличные
balance | Баланс по счету в гривнах\рублях
balance_start | Начальный баланс в гривнах\рублях, остаток денег на счете на момент создания
percent_acquiring | Процент за эквайринг
currency_id | Id валюты в Poster: 1 — гривна, 2 — рубль, 3 — доллар, 4 — евро, 5 — тенге, 6 — лари, 7 — бат, 8 — armenia dram
currency_code | Код валюты на терминале
currency_symbol | Unicode символ валюты, для рубля, драма и маната приходит HTML который на терминале отобразиться как иконка валюты
currency_code_iso | Цифровой код валюты по стандарту ISO 4217
