## menu.getWorkshops: List of Stations

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.getWorkshops'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Response example:

```json
{  
  "response":[  
    {  
      "workshop_id":"1",
      "workshop_name":"Бар",
      "delete":"0"
    },
    {  
      "workshop_id":"2",
      "workshop_name":"Кухня",
      "delete":"0"
    },
    {  
      "workshop_id":"3",
      "workshop_name":"Кондитерская",
      "delete":"0"
    },
    {  
      "workshop_id":"4",
      "workshop_name":"Кальян",
      "delete":"0"
    }
  ]
}
```

The method returns a list of stations

### HTTP request

`GET https://joinposter.com/api/menu.getWorkshops`

### The menu.getWorkshops response parameters

Parameter | Description
--------- | -----------
response | An array of objects

Inside the `response` parameter, there is an array, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
workshop_id | Station ID
workshop_name | Station name
delete | The status of a station having been removed: 0—have not been removed, 1—have been removed

