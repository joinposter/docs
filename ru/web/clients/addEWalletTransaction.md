## clients.addEWalletTransaction: Списание с депозитного счета клиента

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/clients.addEWalletTransaction'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$ewallet = [
  'client_id' => 1,
  'amount'    => 200,
];

$data = sendRequest($url, 'post', $ewallet);
```

> Пример ответа:

```json
{  
   "response":"1"
}
```
 
Метод списывает с депозитного счета клиента

### HTTP POST запрос

`POST https://joinposter.com/api/clients.addEWalletTransaction`

### POST-параметры запроса clients.addEWalletTransaction

Параметр | Описание
-------- | --------
client_id | Id клиента 
amount | Сумма, которая списывается с депозитного счета клиента

### Параметры ответа clients.addEWalletTransaction

Параметр | Описание
-------- | --------
response | id, транзакции списания с депозитного счета
