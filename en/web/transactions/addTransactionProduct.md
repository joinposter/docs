## transactions.addTransactionProduct: Add a Product to an Order

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/transactions.addTransactionProduct'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$transaction = [
    'spot_id'        => 1,
    'spot_tablet_id' => 1,
    'transaction_id' => 1950,
    'product_id'     => 112,
    'modification'   => '[{"m":19,"a":1}]',
];

$data = sendRequest($url, 'post', $transaction);
```

> Response example:

```json
{  
  "response":{  
    "transaction_product":10990
  }
}
```

The method adds a product to an order

### HTTP request

`POST https://joinposter.com/api/transactions.addTransactionProduct`

### POST parameters of the transactions.addTransactionProduct request

Parameter | Description
--------- | -----------
spot_id | Location ID
spot_tablet_id | Register ID
transaction_id | Order ID
product_id | Product or dish ID
modificator_id | Product modifier ID; is not transmitted by default
modification | Dish modifications; are not transmitted by default
price | A product of dish cost; if it should be different from the base cost, it will not be transmitted by default
time | Operation time in the microtime format; the default time is current

The `modification` parameter should contain a JSON `line`. JSON should consist of an array of objects, each of which should contain the following parameters:

Parameter | Description
--------- | -----------
m | Dish modification ID
a | Dish modifications count

### Parameters of the transactions.addTransactionProduct response

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
transaction_product | Product ID added to the current order

During the running, common errors can occur; see the [Error Codes](/en/docs/v3/web/errors) section for their description.

