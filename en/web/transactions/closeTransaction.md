## transactions.closeTransaction: Close an Order

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/transactions.closeTransaction'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$transaction = [
    'spot_id'        => 1,
    'spot_tablet_id' => 1,
    'transaction_id' => 1950,
    'payed_cash'     => 1000,
];

$data = sendRequest($url, 'post', $transaction);
```

> Response example:

```json
{  
  "response":{  
    "err_code":0
  }
}
```

The method closes the order

### HTTP request

`POST https://joinposter.com/api/transactions.closeTransaction`

### POST parameters of the transactions.closeTransaction request

Parameter | Description
--------- | -----------
spot_id | Location ID
spot_tablet_id | Register ID
transaction_id | Order ID
payed_cash | The amount paid by cash
payed_card | The amount paid by bank transfer
payed_cert | The amount paid by a gift card
reason | Reason for closing the bill without payment: 1—the customer has left, 2—on the house, 3—a waiter’s error A mandatory property for closing a bill without payment; the total amount of payments must be equal to zero. By default, it is not transmitted.
print_fiscal | Print a fiscal receipt: 0 — not to print, 1 — print. The default value is 0.
time | Operation time in the microtime format; the default time is current

### transactions.closeTransaction response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
err_code | 0 if the order has been successfully closed

During the running, common errors can occur; see the [Error Codes](/en/docs/v3/web/errors) section for their description.

