## menu.updateWorkshop: Update Station Properties

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.updateWorkshop'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$workshop = [
    'workshop_id'  => 5,
    'product_name' => 'Суши',
];

$data = sendRequest($url, 'post', $workshop);
```

> Response example:

```json
{  
  "response":5
}
```

The method updates the station properties

### HTTP request

`GET https://joinposter.com/api/menu.updateWorkshop`

### POST parameters of the menu.updateWorkshop request

Parameter | Description
--------- | -----------
workshop_id | Station ID
workshop_name | Station name

### The menu.updateWorkshop response parameters

Parameter | Description
--------- | -----------
response | The updated station ID

