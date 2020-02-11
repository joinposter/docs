## clients.removeGroup: Remove a Customer Group

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/clients.removeGroup?'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$group = [
  'group_id' => 6,
];

$data = sendRequest($url, 'post', $group);
```

> Response example:

```json
{
  "response":true
}
```

The method removes a customer group

!> Removed data is not recoverable!
### HTTP request

`POST https://joinposter.com/api/clients.removeGroup`

### POST parameters of the clients.removeGroup request

Parameter | Description
--------- | -----------
group_id | Customer group ID

### The clients.removeGroup response parameters

Parameter | Description
--------- | -----------
response | true, if the customer group has been successfully deleted

