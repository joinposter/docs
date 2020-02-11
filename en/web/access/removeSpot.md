## access.removeSpot: Remove a Location

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/access.removeSpot'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$spot = [
    'spot_id' => 1,
];

$data = sendRequest($url, 'post', $spot);
```

> Response example:

```json
{  
  "response":true
}
```

The method removes a location

### HTTP POST request

`https://joinposter.com/api/access.removeSpot`

### POST parameters of the access.removeSpot request

Parameter | Description
--------- | -----------
spot_id | Location ID

### The access.removeSpot response parameters

Parameter | Description
--------- | -----------
response | `true` if the location has been successfully removed

