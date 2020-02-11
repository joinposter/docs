## finance.createTransactions: Создание новой транзакции

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/finance.createTransactions'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$transaction = [
    'id'            => 1,
    'type'          => 2,
    'category'      => 7,
    'user_id'       => 4,
    'amount_from'   => 1000,
    'amount_to'     => 900,
    'account_from'  => 1,
    'account_to'    => 2,
    'date'          => '16112017',
];

$data = sendRequest($url, 'post', $transaction);

```

> Пример ответа:

```json
{
  "response":600
}
```

Метод создает новую транзакцию 

### HTTP запрос

`POST https://joinposter.com/api/finance.createTransactions`

### POST-параметры запроса finance.createTransactions

Параметр | Описание
-------- | --------
id | Id группы 
type | Тип транзакции: 0 — расход, 1 — доход, 2 — перевод
category | id категории
user_id | id пользователя
date | Дата дата добавления в формате `dmY`

В зависимости от параметра `type` нужно передавать дополнительные параметры 

### type — 0 
Параметр | Описание
-------- | --------
amount_from | Сумма расхода в гривнах\рублях 
account_from | id счета

### type — 1
Параметр | Описание
-------- | --------
amount_to | Сумма дохода в гривнах\рубляъ 
account_to | id счета 

### type — 2
Параметр | Описание
-------- | --------
account_to | id счета на который переводим деньги 
account_from | id  счета с которого делаем перевод
amount_to | Сумма перевода на счет в гривнах\рублях  
amount_from | Сумма перевода со счета в гривнах\рублях


### Параметры ответа finance.createTransactions

Параметр | Описание
-------- | --------
response | id созданной транзакции
