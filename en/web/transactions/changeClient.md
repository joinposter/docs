## transactions.changeClient: Add a Customer to an Order

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/transactions.changeClient'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$transaction = [
    'spot_id'        => 1,
    'spot_tablet_id' => 1,
    'transaction_id' => 1950,
    'client_id'      => 3,
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

The method adds a customer to an order

### HTTP request

`POST https://joinposter.com/api/transactions.changeClient`

### POST parameters of the transactions.changeClient request

Parameter | Description
--------- | -----------
spot_id | Location ID
spot_tablet_id | Register ID
transaction_id | Order ID
client_id | Customer ID
time | Operation time in the microtime format; the default time is current

### The transaction.changeClient response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
err_code | 0 if a customer has been successfully added to an order

During the running, common errors can occur; see the [Error Codes](/en/docs/v3/web/errors) section for their description.

