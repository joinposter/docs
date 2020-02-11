## transactions.changeRecipientFor54FZ: Указание адресата

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/transactions.changeRecipientFor54FZ'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$transaction = [
    'spot_id'        => 1,
    'spot_tablet_id' => 1,
    'transaction_id' => 1950,
    'type'           => 'email',
    'contact'        => 'admin@sample.com',
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

Метод указывает адресат для получения копии фискального чека по 54-ФЗ

### HTTP запрос

`POST https://joinposter.com/api/transactions.changeRecipientFor54FZ`

### POST-параметры запроса transactions.changeRecipientFor54FZ

Параметр | Описание
-------- | --------
spot_id | Id заведения
spot_tablet_id | Id терминала
transaction_id | Id чека
type | Способ отправления копии фискального чека: email — через эл. почту, phone — через SMS (не передавать свойство, если нужно отвязать получателя)
contact | Контакт получателя: эл. почта или номер телефона
time | Время операции в формате microtime, по умолчанию принимает текущее время

### Параметры ответа transactions.changeRecipientFor54FZ

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит объект, внутри которого есть следующие параметры:

Параметр | Описание
-------- | --------
err_code | 0, если метод успешно отработал

В ходе выполнения могут произойти общие ошибки, их описание находится в разделе [Коды ошибок](/docs/v3/web/errors).
