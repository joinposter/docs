## menu.createWorkshop: Create a Station

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.createWorkshop'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$workshop = [
    'workshop_name' => 'Мангал',
];

$data = sendRequest($url, 'post', $workshop);
```

> Response example:

```json
{  
  "response":5
}
```

The method creates a station

### HTTP request

`GET https://joinposter.com/api/menu.createWorkshop`

### POST parameters of the menu.createWorkshop request

Parameter | Description
--------- | -----------
workshop_name | A mandatory parameter, a station name

### The menu.createWorkshop response parameters

Parameter | Description
--------- | -----------
response | The created station ID

