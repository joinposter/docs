## transactions.changeComment: Добавление комментария в чек

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/transactions.changeComment'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$transaction = [
    'spot_id'        => 1,
    'spot_tablet_id' => 1,
    'transaction_id' => 1950,
    'comment'        => 'День рождения',
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

Метод добавляет комментарий в чек

### HTTP запрос

`POST https://joinposter.com/api/transactions.changeComment`

### POST-параметры запроса transactions.changeComment

Параметр | Описание
-------- | --------
spot_id | Id заведения
spot_tablet_id | Id терминала
transaction_id | Id чека
comment | Комментарий к чеку
time | Время операции в формате microtime, по умолчанию принимает текущее время

### Параметры ответа transactions.changeComment

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит объект, внутри которого есть следующие параметры:

Параметр | Описание
-------- | --------
err_code | 0, если комментарий успешно добавлен

В ходе выполнения могут произойти общие ошибки, их описание находится в разделе [Коды ошибок](/docs/v3/web/errors).
