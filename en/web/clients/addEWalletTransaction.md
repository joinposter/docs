## clients.addEWalletTransaction: Withdrawal from a customer’s e-Wallet

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/clients.addEWalletTransaction'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$ewallet = [
  'client_id' => 1,
  'amount'    => 200,
];

$data = sendRequest($url, 'post', $ewallet);
```

> Response example:

```json
{  
   "response":"1"
}
```
 
The method withdrawals a customer’s e-Wallet funds

### HTTP request

`POST https://joinposter.com/api/clients.addEWalletTransaction`

### POST parameters of the clients.addEWalletTransaction request

Parameter | Description
-------- | --------
client_id | Customer ID 
amount | The sum that is transferred from the customer’s e-Wallet

### The clients.addEWalletTransaction response parameters

Parameter | Description
-------- | --------
response | id, e-Wallet withdrawal transactions
