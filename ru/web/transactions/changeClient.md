## transactions.changeClient: Добавление клиента в чек

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/transactions.changeClient'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$transaction = [
    'spot_id'        => 1,
    'spot_tablet_id' => 1,
    'transaction_id' => 1950,
    'client_id'      => 3,
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

Метод добавляет клиента в чек

### HTTP запрос

`POST https://joinposter.com/api/transactions.changeClient`

### POST-параметры запроса transactions.changeClient

Параметр | Описание
-------- | --------
spot_id | Id заведения
spot_tablet_id | Id терминала
transaction_id | Id чека
client_id | Id клиента
time | Время операции в формате microtime, по умолчанию принимает текущее время

### Параметры ответа transactions.changeClient

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит объект, внутри которого есть следующие параметры:

Параметр | Описание
-------- | --------
err_code | 0, если клиент успешно добавлен в чек

В ходе выполнения могут произойти общие ошибки, их описание находится в разделе [Коды ошибок](/docs/v3/web/errors).
