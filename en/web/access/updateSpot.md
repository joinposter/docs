## access.updateSpot: Update Location Properties

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/access.updateSpot'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$spot = [
    'spot_id'   => 2,
    'spot_name' => 'New name',
];

$data = sendRequest($url, 'post', $spot);
```

> Response example:

```json
{  
  "response":2
}
```

The method updates the location properties

### HTTP POST request

`https://joinposter.com/api/access.updateSpot`

### POST parameters of the access.updateSpot request

Parameter | Description
--------- | -----------
spot_id | Location ID
spot_name | Location name

### The access.updateSpot response parameters

Parameter | Description
--------- | -----------
response | The updated location ID

