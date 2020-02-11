## clients.sendSms: Send an SMS from the Account

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/clients.sendSms'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$sms = [
    'phone' => 380684113524,
    'message' => 'У вас осталось 10 бонусов на счету'
];

$data = sendRequest($url, 'post', $sms);

```

> Response example:

```json
{
  "response":true
}
```

The method sends an SMS from the Poster account.

<aside class="warning">
    SMS will be paid separately. The cost is 25 cent per message. 
    This method is available only for paid Poster customers.
</aside>

<aside class="info">
    At the moment, an SMS can be sent only to Russian and Ukrainian numbers. 
    Russian numbers should start with 7, Ukrainian—with 380.
</aside>

### HTTP request

`POST https://joinposter.com/api/clients.sendSms`

### POST parameters of the clients.sendSms request

Parameter | Description
--------- | -----------
phone | The telephone number to which an SMS is sent. The number must be in an international format, without the initial +.
message | SMS message text

### The clients.sendSms response parameters

Parameter | Description
--------- | -----------
response | Result of sending an SMS: `` true—if sent, otherwise the error object will return

