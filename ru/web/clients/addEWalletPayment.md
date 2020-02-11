## clients.addEWalletPayment: Пополнение депозитного счета клиента

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/clients.addEWalletPayment'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$ewallet = [
  'client_id'      => 1,
  'transaction_id' => 1,
  'amount'         => 200,
  'type'           => 1,
];

$data = sendRequest($url, 'post', $ewallet);
```

> Пример ответа:

```json
{  
   "response":"1"
}
```
 
Метод пополняет депозитный счет клиента

### HTTP POST запрос

`POST https://joinposter.com/api/clients.addEWalletPayment`

### POST-параметры запроса clients.addEWalletPayment

Параметр | Описание
-------- | --------
client_id | Id клиента 
transaction_id | Id связанного чека
amount | Сумма, которая начисляется на депозитный счет клиента
type | Тип пополнения: 1 — наличными, 2 — карточкой

### Параметры ответа clients.addEWalletPayment

Параметр | Описание
-------- | --------
response | id, транзакции пополнения депозитного счета
