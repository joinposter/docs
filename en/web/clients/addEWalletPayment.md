## clients.addEWalletPayment: Customer’s e-Wallet top up

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/clients.addEWalletPayment'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$ewallet = [
  'client_id'      => 1,
  'transaction_id' => 1,
  'amount'         => 200,
  'type'           => 1,
];

$data = sendRequest($url, 'post', $ewallet);
```

> Response example:

```json
{  
   "response":"1"
}
```
 
The method tops up a customer’s e-Wallet

### HTTP request

`POST https://joinposter.com/api/clients.addEWalletPayment`

### POST parameters of the clients.addEWalletPayment request

Parameter | Description
-------- | --------
client_id | Customer ID 
transaction_id | Associated order ID
amount | The sum that is transferred to a customer’s e-Wallet
type | The top up method: 1 — in cash, 2 — with id card, e-Wallet transactions

### The clients.addEWalletPayment response parameters

Parameter | Description
-------- | --------
response | Id, e-Wallet transactions
