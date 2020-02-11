## access.createSpot: Create a Location

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/access.createSpot'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$spot = [
    'spot_name' => 'My new spot',
];

$data = sendRequest($url, 'post', $spot);
```

> Response example:

```json
{  
  "response":2
}
```

The method creates a location

### HTTP POST request

`https://joinposter.com/api/access.createSpot`

### POST parameters of the access.createSpot request

Parameter | Description
--------- | -----------
spot_name | Location name

### The access.createSpot response parameters

Parameter | Description
--------- | -----------
response | The created location ID

