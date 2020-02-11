## transactions.changeRecipientFor54FZ: Specify the Recipient

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/transactions.changeRecipientFor54FZ'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$transaction = [
    'spot_id'        => 1,
    'spot_tablet_id' => 1,
    'transaction_id' => 1950,
    'type'           => 'email',
    'contact'        => 'admin@sample.com',
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

The method specifies the recipient of a 54-FZ fiscal receipt copy

### HTTP request

`POST https://joinposter.com/api/transactions.changeRecipientFor54FZ`

### POST parameters of the transactions.changeRecipientFor54FZ request

Parameter | Description
--------- | -----------
spot_id | Location ID
spot_tablet_id | Register ID
transaction_id | Order ID
type | Method of sending a fiscal receipt copy: email—via email, phone—via an SMS (do not transmit the property if you need to detach the recipient)
contact | Recipient contact details: email or phone number
time | Operation time in the microtime format; the default time is current

### transactions.changeRecipientFor54FZ response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
err_code | 0 if the method has successfully worked

During the running, common errors can occur; see the [Error Codes](/en/docs/v3/web/errors) section for their description.

