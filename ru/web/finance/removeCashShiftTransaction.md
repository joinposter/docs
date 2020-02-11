## finance.removeCashShiftTransaction: Удаление транзакции кассовой смены

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/finance.removeCashShiftTransaction'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$cash_shift_transaction = [
    'cash_shift_transaction_id' => 611,
];

$data = sendRequest($url, 'post', $cash_shift_transaction);
```

> Пример ответа:

```json
{  
  "response":true
}
```

Метод удаляет транзакцию кассовой смены. 
!>     Удалять транзакцию кассовой смены можно только с типом "Доход", "Расход" или "Инкассация"

### HTTP запрос

`GET https://joinposter.com/api/finance.removeCashShiftTransaction`

### POST-параметры запроса finance.removeCashShiftTransaction

Параметр | Описание
-------- | --------
cash_shift_transaction_id | Id транзакции кассовой смены

### Параметры ответа finance.removeCashShiftTransaction

Параметр | Описание
--------- | -----------
response | true, если транзакция кассовой смены успешно удалена
