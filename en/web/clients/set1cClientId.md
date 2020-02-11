## clients.set1cClientId: Update the Customer ID in the 1C System

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/clients.set1cClientId'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$client = [
    'id' => [
        [
            'client_id' => 38,
            'id_1c'     => 'b80ffc81-0fc9-11e7-9ab4-ace01035e460',
        ],
    ],
];

$data = sendRequest($url, 'post', $client);
```

> Response example:

```json
{  
  "success":1
}
```

The method updates the customer ID in the 1C system

### HTTP request

`GET https://joinposter.com/api/clients.set1cClientId`

### POST parameters of the clients.set1cClientId request

Parameter | Description
--------- | -----------
id | An array of objects

Each object, in turn, must contain the following properties:

Parameter | Description
--------- | -----------
client_id | Customer ID
id_1c | Customer ID in the 1C system

### The clients.set1cClientId response parameters

Parameter | Description
--------- | -----------
success | 1 if the customer ID in the 1C system has been successfully updated

