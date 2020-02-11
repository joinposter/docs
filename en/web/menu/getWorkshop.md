## menu.getWorkshop: Station Properties

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.getWorkshop'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&workshop_id=1';

$data = sendRequest($url);
```

> Response example:

```json
{  
  "response":{  
    "workshop_id":"1",
    "workshop_name":"Бар",
    "delete":"0"
  }
}
```

The method returns the station properties

### HTTP request

`GET https://joinposter.com/api/menu.getWorkshop`

### GET parameters of the menu.getWorkshop request

Parameter | Description
--------- | -----------
workshop_id | Station ID

### The menu.getWorkshop response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
workshop_id | Station ID
workshop_name | Station name
delete | The status of a station having been removed: 0—have not been removed, 1—have been removed

