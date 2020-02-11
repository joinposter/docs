## transactions.createTransaction: Создание чека

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/transactions.createTransaction'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$transaction = [
    'spot_id'        => 1,
    'spot_tablet_id' => 1,
    'table_id'       => 1,
    'user_id'        => 3,
    'guests_count'   => 2,
];

$data = sendRequest($url, 'post', $transaction);
```

> Пример ответа:

```json
{  
  "response":{  
    "transaction_id":1950,
    "transaction_tablet_id":1508850241000
  }
}
```

Метод создаёт чек

### HTTP запрос

`POST https://joinposter.com/api/transactions.createTransaction`

### POST-параметры запроса transactions.createTransaction

Параметр | Описание
-------- | --------
spot_id | Id заведения в котором нужно создать чек
spot_tablet_id | Id терминала в котором нужно создать чек
table_id | Id стола
user_id | Id сотрудника
guests_count | Количество гостей за столом
time | Время операции в формате microtime, по умолчанию принимает текущее время

### Параметры ответа transactions.createTransaction

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит объект, внутри которого есть следующие параметры:

Параметр | Описание
-------- | --------
transaction_id | Id созданного чека, соответсвует номеру чека
transaction_tablet_id | Id созданного чека на терминале, соответствует времени открытия чека

В ходе выполнения могут произойти общие ошибки, их описание находится в разделе [Коды ошибок](/docs/v3/web/errors).
