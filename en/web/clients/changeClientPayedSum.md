## clients.changeClientPayedSum: Update the Customer Total Purchase Sum

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/clients.changeClientPayedSum'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$sum = [
  'client_id' => 50,
  'count'     => 20,
];

$data = sendRequest($url, 'post', $sum);
```

> Response example:

```json
{
  "response":110
}
```

The method updates the customer total purchase sum

### HTTP request

`POST https://joinposter.com/api/clients.changeClientPayedSum`

### POST parameters of the clients.changeClientPayedSum request

Parameter | Description
--------- | -----------
client_id | Customer ID
count | The purchase sum to be accrued to the customer. If the count is positive—to accrue; if the count is negative—to write off.
block_webhook | An optional parameter; if it is true, the response won’t contain a webhook on updating the customer’s data

### The clients.changeClientPayedSum response parameters

Parameter | Description
--------- | -----------
response | The total purchase sum that the customer has got after the updates have been made

