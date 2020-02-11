## access.getTablets: Register List

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/access.getTablets'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response":[
    {
      "tablet_id":"1",
      "tablet_name":"Main in Madrid",
      "spot_id":"1"
    }
  ]
}
```

The method returns the register list

### HTTP GET request

`https://joinposter.com/api/access.getTablets`

### The access.getTablets response parameters

Parameter | Description
--------- | -----------
response | An array of objects

Inside the `response` parameter, there is an array, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
tablet_id | Register ID
tablet_name | Register name
spot_id | The ID of the location the register is attached to

