## access.updateTablet: Update Register Properties

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/access.updateTablet'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$tablet = [
    'spot_tablet_id'   => 2,
    'spot_id'          => 1,
    'spot_tablet_name' => 'New tablet',
    'spot_code'        => 'b3ss7m1p',
];

$data = sendRequest($url, 'post', $tablet);
```

> Response example:

```json
{  
  "response":2
}
```

The method updates the register properties

### HTTP POST request

`https://joinposter.com/api/access.updateTablet`

### POST parameters of the access.updateTablet request

Parameter | Description
--------- | -----------
spot_tablet_id | Register ID
spot_id | The ID of the location the register is attached to
spot_tablet_name | Register name
spot_code | Register password

### The access.updateTablet response parameters

Parameter | Description
--------- | -----------
response | The updated register ID

