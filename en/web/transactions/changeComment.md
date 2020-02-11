## transactions.changeComment: Add an Order Comment

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/transactions.changeComment'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$transaction = [
    'spot_id'        => 1,
    'spot_tablet_id' => 1,
    'transaction_id' => 1950,
    'comment'        => 'День рождения',
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

The method adds a comment to an order

### HTTP request

`POST https://joinposter.com/api/transactions.changeComment`

### POST parameters of the transactions.changeComment request

Parameter | Description
--------- | -----------
spot_id | Location ID
spot_tablet_id | Register ID
transaction_id | Order ID
comment | Order comment
time | Operation time in the microtime format; the default time is current

### transaction.changeComment response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
err_code | 0 if a comment has been successfully added

During the running, common errors can occur; see the [Error Codes](/en/docs/v3/web/errors) section for their description.

