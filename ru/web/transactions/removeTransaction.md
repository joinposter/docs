## transactions.removeTransaction: Удаление чека

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/transactions.removeTransaction'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$transaction = [
    'spot_tablet_id' => 1,
    'transaction_id' => 1950,
    'user_id'        => 3,
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

Метод удаляет чек

### HTTP запрос

`POST https://joinposter.com/api/transactions.removeTransaction`

### POST-параметры запроса transactions.removeTransaction

Параметр | Описание
-------- | --------
spot_tablet_id | Id терминала
transaction_id | Id чека
user_id | Id сотрудника
time | Время операции в формате microtime, по умолчанию принимает текущее время

### Параметры ответа transactions.removeTransaction

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит объект, внутри которого есть следующие параметры:

Параметр | Описание
-------- | --------
err_code | 0, если чек успешно удалён

В ходе выполнения могут произойти общие ошибки, их описание находится в разделе [Коды ошибок](/docs/v3/web/errors).
