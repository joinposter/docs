## clients.changeClientBonus: Update the Customer Points Count

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/clients.changeClientBonus'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$bonus = [
  'client_id' => 7,
  'count'     => 10,
];

$data = sendRequest($url, 'post', $bonus);
```

> Response example:

```json
{
  "response":30
}
```

The method updates the customer points count. It is used only for customers with a points-based loyalty program.

### HTTP request

`POST https://joinposter.com/api/clients.changeClientBonus`

### POST parameters of the clients.changeClientBonus request

Parameter | Description
--------- | -----------
client_id | Customer ID
count | The points count to be accrued to the customer. If the count is positive—to accrue; if the count is negative—to write off.
block_webhook | An optional parameter; if it is true, the response won’t contain a webhook on updating the customer’s data

### The clients.changeClientBonus response parameters

Parameter | Description
--------- | -----------
response | The points count that a customer has got after the updates have been made

