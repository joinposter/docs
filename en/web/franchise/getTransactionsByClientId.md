## franchise.getTransactionsByClientId: Customer Transaction List

> Request example:

```php
<?
$url = 'https://joinposter.com/api/franchise.getTransactionsByClientId'
    . '?format=json'
    . '&token=687409:4164553abf6a031302898da7800b59fb'
    . '&client_id=4'
    . '&date_from=20170400';

$transactions = sendRequest($url);
```

> Response example:

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

The method returns the customer transactions for all franchises for the specified period

### HTTP request

`GET https://joinposter.com/api/franchise.getTransactionsByClientId`

### GET parameters of the franchise.getTransactionsByClientId request

Parameter | Description
--------- | -----------
client_id | Customer ID in the master account.
date_from | An optional parameter. The sampling start date (Ymd), inclusive. The default date is a month ago.
date_to | An optional parameter. The sampling end date (Ymd), inclusive. The default date is the current date.

### The franchise.getTransactionsByClientId response parameters

Parameter | Description
--------- | -----------
date_from | The sampling start date
date_to | The sampling end date
transactions_count | Transactions found count
transactions | Transactions list

Inside the `transactions` , there is an array, each element of which contains the following properties:

Parameter | Description
--------- | -----------
franchise_id | The ID of the current transaction franchise
transaction_id | The transaction ID in the current franchise
date_close | Transaction closing date
sum | The total transaction amount
bonus | Transaction points accrued
bonus_payed | Transaction points paid
products | Products list

Inside the `products`, there is an array, each element of which contains the following properties:

Parameter | Description
--------- | -----------
product_id | Product ID in the master account
modificator_id | Product modifier ID in the master account
franchise_product_id | Product ID in the current franchise
franchise_modification_id | Product modifier ID in the current franchise
sum | Product cost

