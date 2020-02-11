## finance.updateTransactions: Update a Transaction

> Request example:

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

> Response example:

```json
{
  "response":600
}
```

The method updates an existing transaction

### HTTP request

`POST https://joinposter.com/api/finance.updateTransactions`

### POST parameters of the finance.createTransactions request

Parameter | Description
--------- | -----------
transaction_id | Transaction ID to update
type | Transaction type: 0—expenditure, 1—income, 2—transfer
category | Category ID
user_id | User ID
date | Date of adding in the `Ymd` format

Depending on the `type` parameter, additional parameters have to be transmitted

### type = 0

Parameter | Description
--------- | -----------
amount_from | Expenditure amount
account_from | Order ID

### type = 1

Parameter | Description
--------- | -----------
amount_to | Amount of income
account_to | Order ID

### type = 2

Parameter | Description
--------- | -----------
account_to | The ID of an account the money is transferred to
account_from | The ID of an account the money is transferred from
amount_to | Transfer amount to accounts
amount_from | Transfer amount from the account

### The finance.updateTransactions response parameters

Parameter | Description
--------- | -----------
response | The updated transaction ID

