## spots.getSpotTablesHalls: Floor Sections List

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/spots.getSpotTablesHalls'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Response example:

```json
{  
  "response":[  
    {  
      "hall_id":"3",
      "hall_name":"Зал в кафе на Полянке",
      "hall_order":"1",
      "spot_id":"1",
      "delete":"0",
      "last_modified_time":"2017-06-22 13:54:58"
    },
    {  
      "hall_id":"5",
      "hall_name":"Зал у львівській кав&#39;ярні",
      "hall_order":"2",
      "spot_id":"2",
      "delete":"0",
      "last_modified_time":"2017-06-22 13:54:58"
    }
  ]
}
```

The method returns the floor sections list

### HTTP request

`GET https://joinposter.com/api/spots.getSpotTablesHalls`

### spots.getSpotTablesHalls response parameters

Parameter | Description
--------- | -----------
response | An array of objects

Inside the `response` parameter, there is an array, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
hall_id | Floor section ID
hall_name | Floor section name
hall_order | Floor section order
spot_id | Location ID
delete | The status of a floor section removed: 0—not removed, 1—removed
last_modified_time | Last update time of the floor section properties

