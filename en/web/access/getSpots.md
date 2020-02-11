## access.getSpots: Locations List

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/access.getSpots'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response":[
    {
      "spot_id":"1",
      "spot_name":"Spot in Madrid",
      "spot_adress":"Rome, Madrid",
      "storages":[
        {
          "storage_id":1,
          "storage_name":"Storage in Madrid",
          "storage_adress":"Rome, Madrid"
        }
      ]
    },
    {
      "spot_id":"2",
      "spot_name":"Spot in Milan",
      "spot_adress":"Rome, Milan",
      "storages":[
        {
          "storage_id":2,
          "storage_name":"Storage in Milan",
          "storage_adress":"Rome, Milan"
        }
      ]
    }
  ]
}
```

The method returns a list of locations

### HTTP GET request

`https://joinposter.com/api/access.getSpots`

### GET parameters of the access.getSpots request

Parameter | Description
--------- | -----------
1c | It allows returning the location 1C system in the response You must transmit true as a value. By default, it is not transmitted.

### The access.getSpots response parameters

Parameter | Description
--------- | -----------
response | An array of objects

Inside the `response` parameter, there is an array, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
spot_id | Location ID
spot_name | Location name
spot_adress | Location address
id_1c | Location ID in the 1C system
storages | Storages attached to the location

The `storages` parameter has an array inside, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
storage_id | Storage ID
storage_name | Storage name
storage_adress | Storage address

