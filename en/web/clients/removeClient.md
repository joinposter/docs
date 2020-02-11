## clients.removeClient: Remove a Customer

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/clients.removeClient'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$client = [
    'client_id' => 2,
];

$data = sendRequest($url, 'post', $client);
```

> Response example:

```json
{  
  "response":true
}
```

The method removes a customer

### HTTP request

`GET https://joinposter.com/api/clients.removeClient`

### POST parameters of the clients.removeClient request

Parameter | Description
--------- | -----------
client_id | Customer ID

### The clients.removeClient response parameters

Parameter | Description
--------- | -----------
response | true if the customer has been successfully removed

