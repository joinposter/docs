## clients.updateClient: Update Customer Properties

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/clients.updateClient'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$client = [
  'client_id'               => 50,
  'client_name'             => 'Попова Елена Андреевна',
  'client_sex'              => 2,
  'client_groups_id_client' => 7,
  'card_number'             => '0000000000222',
  'discount_per'            => 0,
  'phone'                   => '+380 50 22-11-111',
  'email'                   => 'contact@joinposter.com',
  'birthday'                => '1986-11-23',
  'bonus'                   => 10,
  'total_payed_sum'         => 417000,
];

$data = sendRequest($url, 'post', $client);
```

> Response example:

```json
{
  "response":4082
}
```

The method updates the customer properties

### HTTP request

`POST https://joinposter.com/api/clients.updateClient`

### POST parameters of the clients.updateClient request

Parameter | Description
--------- | -----------
client_id | Customer ID
client_name | Customer full name
client_sex | Customer gender: 0—not specified, 1—male, 2—female
client_groups_id_client | Customer group ID
card_number | Customer card number
discount_per | Personal percentage of a discount or points. It will be applied if it is higher than a customer group percentage.
phone | Customer unique phone number, since there cannot be two customers with the same number in the system
email | Customer email address
birthday | Customer birthday in the “Y-m-d” format
city | Customer city
country | Customer country
address | Customer address
comment | Customer account comment
bonus | The current amount of the accumulated customer points
total_payed_sum | Total purchase sum in kopecks

### The clients.updateClient response parameters

Parameter | Description
--------- | -----------
response | Updated customer ID

