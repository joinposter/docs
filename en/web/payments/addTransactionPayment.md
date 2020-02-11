## payments.addTransactionPayment: Customer Order Billing Notification

> Request example:

```php
<?
$url = 'https://joinposter.com/api/payments.addTransactionPayment?' .
  'format=json';

$application_secret = '123123123123';

$payment = [
  'type' => 'application-name',
  'merchant_id' => 3432343,
  'transaction_id' => '1474012061849',
  'payed_sum' => 369.00,
  'credited_sum' => 365.31,
];

$payment['sign'] = md5(implode(':', $payment) . ':' . $application_secret);

$answer = sendRequest($url, 'post', $payment);
```

> Response example:

```json
{
  "response":{
    "status":"accept"
  }
}
```

The Poster system notification of the successful customer order billing through an external payment service.

### HTTP request

`POST https://joinposter.com/api/payments.addTransactionPayment`

### POST parameters of the payments.addTransactionPayment request

Parameter | Description
--------- | -----------
type | The key name of the payment system that sends a request for payment that has come. Under the system, a separate application is created in the Poster system, where the given name is specified.
merchant_id | Poster customer ID in the internal database of the payment system
transaction_id | The ID of the order that has been paid through the payment system
payed_sum | The order amount paid by the visitor (in hryvnias/rubles)
credited_sum | The amount that has been credited to the Poster customer operating account (in hryvnias/rubles). This is the order amount minus the acquiring fee.
sign | The request signature that is an md5 hash of a line connecting the values of the following variables through the colon: type, merchant_id, transaction_id, payed_sum, credited_sum, application_secret.

application_secret is an application secret line. Like the type variable, it is issued to the payment system while creating an application for it in Poster.

### The payments.addTransactionPayment response parameters

Parameter | Description
--------- | -----------
status | If the request is successful, it will contain the accept value

