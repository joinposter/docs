## transactions.removeTransaction: Remove an Order

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/transactions.removeTransaction'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$transaction = [
    'spot_tablet_id' => 1,
    'transaction_id' => 1950,
    'user_id'        => 3,
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

The method removes an order

### HTTP request

`POST https://joinposter.com/api/transactions.removeTransaction`

### POST parameters of the transactions.removeTransaction request

Parameter | Description
--------- | -----------
spot_tablet_id | Register ID
transaction_id | Order ID
user_id | Employee ID
time | Operation time in the microtime format; the default time is current

### transactions.removeTransaction response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
err_code | 0 if the order has been successfully removed

During the running, common errors can occur; see the [Error Codes](/en/docs/v3/web/errors) section for their description.

