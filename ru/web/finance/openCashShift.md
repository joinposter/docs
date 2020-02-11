## finance.openCashShift: Открытие кассовой смены

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/finance.openCashShift'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$cash_shift = [
    'spot_id'   => 1,
    'user_id'   => 1,
    'amount'    => 123.45,
    'time'      => '2017-09-21 10:00',
    'is_fiscal' => 1,
];

$data = sendRequest($url, 'post', $cash_shift);
```

> Пример ответа:

```json
{  
  "response":{  
    "cash_shift_id":333
  }
}
```

Метод открывает кассовую смену

### HTTP запрос

`GET https://joinposter.com/api/finance.openCashShift`

### POST-параметры запроса finance.openCashShift

Параметр | Описание
-------- | --------
spot_id | Id заведения
user_id | Id сотрудника
amount | Сумма в кассе при открытии кассовой смены в гривнах\рублях
time | Дата и время открытия кассовой смены в минутах в формате `Y-m-d H:i`
is_fiscal | Признак, что транзакция открытия кассовой смены фискальная: 0 — не фискальная, 1 — фискальная. По умолчанию принимает 0. 

### Параметры ответа finance.openCashShift

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит объект, внутри которого есть следующие параметры:

Параметр | Описание
-------- | --------
cash_shift_id | Id открытой кассовой смены
