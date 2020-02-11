## finance.getCashShift: Свойства кассовой смены

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/finance.getCashShift'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&cash_shift_id=333';

$data = sendRequest($url);
```

> Пример ответа:

```json
{  
  "response":{  
    "cash_shift_id":333,
    "spot_id":1,
    "timestart":1505977200000,
    "timeend":1505980800000,
    "amount_start":10000,
    "amount_end":10000,
    "amount_debit":0,
    "amount_sell_cash":0,
    "amount_sell_card":0,
    "amount_credit":0,
    "amount_collection":0,
    "user_id_start":3,
    "user_id_end":3,
    "comment":"бар"
  }
}
```

Метод возвращает свойства кассовой смены

### HTTP запрос

`GET https://joinposter.com/api/finance.getCashShift`

### GET-параметры запроса finance.getCashShift

Параметр | Описание
-------- | --------
cash_shift_id | Обязательный параметр, id кассовой смены

### Параметры ответа finance.getCashShift

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит объект, внутри которого есть следующие параметры:

Параметр | Описание
-------- | --------
cash_shift_id | Id кассовой смены
spot_id | Id заведения
timestart | Дата и время открытия кассовой смены, формат microtime
timeend | Дата и время закрытия кассовой смены, формат microtime
amount_start | Сумма в кассе при открытии кассовой смены в копейках
amount_end | Сумма в кассе при закрытии кассовой смены в копейках
amount_debit | Сумма приходов в копейках
amount_sell_cash | Сумма выручки наличной оплаты в копейках
amount_sell_card | Сумма выручки безналичной оплаты в копейках
amount_credit | Сумма расходов в копейках
amount_collection | Сумма инкассаций в копейках
user_id_start | Id сотрудника открывшего кассовую смену
user_id_end | Id сотрудника закрывшего кассовую смену
comment | Комментарий
