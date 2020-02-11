## finance.createTransactions: Create a New Transaction

> Request example:

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

> Response example:

```json
{
  "response":600
}
```

The method creates a new transaction

### HTTP request

`POST https://joinposter.com/api/finance.createTransactions`

### POST parameters of the finance.createTransactions request

Parameter | Description
--------- | -----------
id | Group ID
type | Transaction type: 0—expenditure, 1—income, 2—transfer
category | Category ID
user_id | User ID
date | Date of adding in the `dmY` format

Depending on the `type` parameter, additional parameters have to be transmitted

### type — 0

Parameter | Description
--------- | -----------
amount_from | The amount of expenditure in hryvnias/rubles
account_from | Order ID

### type — 1

Parameter | Description
--------- | -----------
amount_to | The amount of income in hryvnias/rubles
account_to | Order ID

### type—2

Parameter | Description
--------- | -----------
account_to | The ID of an account the money is transferred to
account_from | The ID of an account the money is transferred from
amount_to | The amount of transfer to the account in hryvnias/rubles
amount_from | The amount of transfer from the account in hryvnias/rubles

### The finance.createTransactions response parameters

Parameter | Description
--------- | -----------
response | The created transaction ID

