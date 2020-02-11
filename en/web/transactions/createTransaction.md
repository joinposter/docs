## transactions.createTransaction: Create an Order

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/transactions.createTransaction'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$transaction = [
    'spot_id'        => 1,
    'spot_tablet_id' => 1,
    'table_id'       => 1,
    'user_id'        => 3,
    'guests_count'   => 2,
];

$data = sendRequest($url, 'post', $transaction);
```

> Response example:

```json
{  
  "response":{  
    "transaction_id":1950,
    "transaction_tablet_id":1508850241000
  }
}
```

The method creates an order

### HTTP request

`POST https://joinposter.com/api/transactions.createTransaction`

### POST parameters of the transactions.createTransaction request

Parameter | Description
--------- | -----------
spot_id | Location ID to create an order for
spot_tablet_id | Register ID to create an order in
table_id | Table ID
user_id | Employee ID
guests_count | Table seat count
time | Operation time in the microtime format; the default time is current

### Parameters of the transaction.createTransaction response

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
transaction_id | Created order ID, corresponds to the order number
transaction_tablet_id | The ID of the order created on the register, corresponds to the order opening time

During the running, common errors can occur; see the [Error Codes](/en/docs/v3/web/errors) section for their description.

