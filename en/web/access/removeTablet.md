## access.removeTablet: Remove a Register

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/access.removeTablet'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$tablet = [
    'spot_tablet_id' => 1,
];

$data = sendRequest($url, 'post', $tablet);
```

> Response example:

```json
{  
  "response":true
}
```

The method removes a register

### HTTP POST request

`https://joinposter.com/api/access.removeTablet`

### POST parameters of the access.removeTablet request

Parameter | Description
--------- | -----------
spot_tablet_id | Register ID

### The access.removeTablet response parameters

Parameter | Description
--------- | -----------
response | `true` if the register has been successfully removed
