## franchise.getTransactionsByClientId: Список транзакций клиента

>  Пример запроса:

```php
<?
$url = 'https://joinposter.com/api/franchise.getTransactionsByClientId'
    . '?format=json'
    . '&token=687409:4164553abf6a031302898da7800b59fb'
    . '&client_id=4'
    . '&date_from=20170400';

$transactions = sendRequest($url);
```

> Пример ответа:

```json
{
  "response": {
    "date_from": "2017-04-01 00:00:00",
    "date_to": "2017-04-30 23:59:59",
    "transactions_count": 2,
    "transactions": [
      {
        "franchise_id": 7457,
        "transaction_id": 12870,
        "date_close": "2017-04-25 17:58:50",
        "sum": 246.4,
        "bonus": 0,
        "bonus_payed": 0,
        "products": [
          {
            "product_id": 832,
            "modificator_id": 0,
            "franchise_product_id": 322,
            "franchise_modification_id": 0,
            "sum": 246.4
          }
        ]
      },
      {
        "franchise_id": 888,
        "transaction_id": 44626,
        "date_close": "2017-04-12 16:25:42",
        "sum": 626,
        "bonus": 0,
        "bonus_payed": 0,
        "products": [
          {
            "product_id": 13,
            "modificator_id": 0,
            "franchise_product_id": 13,
            "franchise_modification_id": 0,
            "sum": 318
          },
          {
            "product_id": 10,
            "modificator_id": 0,
            "franchise_product_id": 10,
            "franchise_modification_id": 0,
            "sum": 308
          }
        ]
      }
    ]
  }
}
```

Метод возвращает транзакции клиента по всем франшизам за указанный период

### HTTP запрос

`GET https://joinposter.com/api/franchise.getTransactionsByClientId`

### GET-параметры запроса franchise.getTransactionsByClientId

Параметр  | Описание
--------- | ---------
client_id | Id клиента в мастер-аккаунте.
date_from | Опциональный параметр. Дата начала выборки (Ymd), включительно. По умолчанию дата месяц назад.
date_to | Опциональный параметр. Дата конца выборки (Ymd), включительно. По умолчанию дата текущего дня.

### Параметры ответа franchise.getTransactionsByClientId

Параметр  | Описание
--------- | ---------
date_from | Дата начала выборки
date_to | Дата конца выборки
transactions_count | Количество найденных транзакций 
transactions | Список транзакций

Внутри `transactions` лежит массив, в каждом элементе которого есть следующие свойства:

Параметр  | Описание
--------- | ---------
franchise_id | Id франшизы текущей транзакции
transaction_id | Id транзакции в текущей франшизе
date_close | Дата закрытия транзакции
sum | Общая сумма по транзакции
bonus | Начисленные бонусы по транзакции
bonus_payed | Оплаченные бонусы по транзакции
products | Список продуктов

Внутри `products` лежит массив, в каждом элементе которого есть следующие свойства:

Параметр  | Описание
--------- | ---------
product_id | Id продукта в мастер-аккаунте
modificator_id | Id модификатора продукта в мастер-аккаунте
franchise_product_id | Id продукта в текущей франшизе
franchise_modification_id | Id модификатора продукта в текущей франшизе
sum | Стоимость продукта
