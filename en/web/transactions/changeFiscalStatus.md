## transactions.changeFiscalStatus: Change fiscal status

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/transactions.changeFiscalStatus'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$postData = [
    'transaction_id' => 1322,
    'products' => [
        [
            'product_id' => 120,
            'promotion_id' => 2,
            'modification_id' => 24,
            'count' => 3,   
        ],
        [
            'product_id' => 122,
            'promotion_id' => 0,
            'modification_id' => 0,
            'count' => 0.350,   
        ],
    ],
];

$data = sendRequest($url, 'post', $postData);
```

> Response example:

```json
{
   "response":{
      "err_code":0
   }
}
```

The method changes order's fiscal status to – fiscal receipt printed. If `fiscal_return` parameter was sent, status will be changed to – fiscal return. 


### HTTP request

`POST https://joinposter.com/api/transactions.changeFiscalStatus`

### POST parameters of the transactions.changeFiscalStatus request

Parameter | Description
--------- | -----------
transaction_id | Order Id
fiscal_return | Optional parameter, indicates fiscal return: `true` – fiscal receipt was returned, `false` – fiscal receipt was printed. The default value is `false`.  
time | Optional parameter, time in the microtime format. The default time is current

Inside the `products` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
product_id | Product or dish Id
modification_id | Modification Id
promotion_id | Product or dish promotion Id
count | Count of printed or returned products

### transaction.changeFiscalStatus response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
err_code | Status change result, 0 — receipt status was changed

During the running, common errors can occur, see the [Error Codes](/en/docs/v3/web/errors) section for their description.

