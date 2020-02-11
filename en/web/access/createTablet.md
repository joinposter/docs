## access.createTablet: Create a Register

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/access.createTablet'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$tablet = [
    'spot_id'          => 1,
    'spot_tablet_name' => 'My new tablet',
    'spot_code'        => 'crsa5a54',
];

$data = sendRequest($url, 'post', $tablet);
```

> Response example:

```json
{  
  "response":2
}
```

The method creates a register

### HTTP POST request

`https://joinposter.com/api/access.createTablet`

### POST parameters of the access.createTablet request

Parameter | Description
--------- | -----------
spot_id | The ID of the location the register will be attached to
spot_tablet_name | Register name
spot_code | Register password

### The access.createTablet response parameters

Parameter | Description
--------- | -----------
response | The created register ID

