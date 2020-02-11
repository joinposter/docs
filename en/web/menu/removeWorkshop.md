## menu.removeWorkshop: Remove a Station

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.removeWorkshop'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$workshop = [
    'workshop_id' => 2,
];

$data = sendRequest($url, 'post', $workshop);
```

> Response example:

```json
{  
  "response":true
}
```

The method removes a station

### HTTP request

`GET https://joinposter.com/api/menu.removeWorkshop`

### POST parameters of the menu.removeWorkshop request

Parameter | Description
--------- | -----------
workshop_id | Station ID

### The menu.removeWorkshop response parameters

Parameter | Description
--------- | -----------
response | true if the station has been successfully removed

