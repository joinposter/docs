## finance.updateAccount: Update an Account

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/finance.updateAccount'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$account = [
    'account_id' => 3,
    'account_name' => 'Сейф',
    'currency_id' => 3,
    'type' => 1,
    'balance_start' => 0,
];

$data = sendRequest($url, 'post', $account);

```

> Response example:

```json
{
  "response":4
}
```

The method updates the account properties

### HTTP request

`POST https://joinposter.com/api/finance.updateAccount`

### POST parameters of the finance.updateAccount request

Parameter | Description
--------- | -----------
account_id | Order ID
account_name | Account name
type | Type of account: 1—non-cash, 2—bank card, 3—cash
balance_start | The balance of money at the time of creation, in hryvnias/rubles
currency_id | Currency ID in Poster: 1—hryvnia, 2—ruble, 3—dollar, 4—euro, 5—tenge, 6—lari, 7—baht, 8—Armenian dram

### The finance.updateAccount response parameters

Parameter | Description
--------- | -----------
response | The updated account ID

