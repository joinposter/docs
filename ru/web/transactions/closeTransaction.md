## transactions.closeTransaction: Закрытие чека

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/transactions.closeTransaction'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$transaction = [
    'spot_id'        => 1,
    'spot_tablet_id' => 1,
    'transaction_id' => 1950,
    'payed_cash'     => 1000,
];

$data = sendRequest($url, 'post', $transaction);
```

> Пример ответа:

```json
{  
  "response":{  
    "err_code":0
  }
}
```

Метод закрывает чек

### HTTP запрос

`POST https://joinposter.com/api/transactions.closeTransaction`

### POST-параметры запроса transactions.closeTransaction

Параметр | Описание
-------- | --------
spot_id | Id заведения
spot_tablet_id | Id терминала
transaction_id | Id чека
payed_cash | Сумма оплаты наличным расчётом
payed_card | Сумма оплаты безналичным расчётом
payed_cert | Сумма оплаты сертификатом
reason | Причина закрытия чека без оплаты: 1 — гость ушел, 2 — за счёт заведения, 3 — ошибка официанта. Обязательное поле для закрытия чека без оплаты, сумма всех оплат должна быть равна нулю. По умолчанию не передаётся.
print_fiscal | Печатать фискального чека: 0 — не печатать, 1 — печатать. По умолчанию принимает 0.
time | Время операции в формате microtime, по умолчанию принимает текущее время

### Параметры ответа transactions.closeTransaction

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит объект, внутри которого есть следующие параметры:

Параметр | Описание
-------- | --------
err_code | 0, если чек успешно закрыт

В ходе выполнения могут произойти общие ошибки, их описание находится в разделе [Коды ошибок](/docs/v3/web/errors).
