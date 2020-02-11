## finance.updateTransactions: Изменение транзакции

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/finance.updateTransactions'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$transaction = [
    'transaction_id'    => 600,
    'type'              => 2,
    'category'          => 7,
    'user_id'           => 4,
    'amount_from'       => 1000,
    'amount_to'         => 900,
    'account_from'      => 1,
    'account_to'        => 2,
    'date'              => '16112017',
];

$data = sendRequest($url, 'post', $transaction);

```

> Пример ответа:

```json
{
  "response":600
}
```

Метод изменяет существующую транзакцию

### HTTP запрос

`POST https://joinposter.com/api/finance.updateTransactions`

### POST-параметры запроса finance.createTransactions

Параметр | Описание
-------- | --------
transaction_id | Id транзакции для обновления  
type | Тип транзакции: 0 — расход, 1 — доход, 2 — перевод
category | id категории
user_id | id пользователя
date | Дата дата добавления в формате `Ymd`

В зависимости от параметра `type` нужно передавать дополнительные параметры 

### type = 0 
Параметр | Описание
-------- | --------
amount_from | сумма расхода   
account_from | id  счета

### type = 1
Параметр | Описание
-------- | --------
amount_to | сумма дохода 
account_to | id  счета 

### type = 2
Параметр | Описание
-------- | --------
account_to | id счета на который переводим деньги 
account_from | id  счета с которого делаем перевод
amount_to | сумма перевода на счета  
amount_from | сумма перевода со счета

### Параметры ответа finance.updateTransactions

Параметр | Описание
-------- | --------
response | id измененной транзакции
