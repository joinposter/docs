## franchise.getSpots: List of Franchisee Locations throughout the Franchise

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/franchise.getSpots'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);

```

> Response example:

```json
{  
   "response":{  
      "demo-franchisee":[  
         {  
            "spot_id":1,
            "name":"Демо франчайзи",
            "address":""
         },
         {  
            "spot_id":2,
            "name":"Демо франчайзи2",
            "address":""
         }
      ]
   }
}
```

The method returns the list of franchisee locations throughout the franchise

### HTTP GET request

`GET https://joinposter.com/api/franchise.getSpots`

### The franchise.getSpots response parameters

Parameter | Description
--------- | -----------
response | An array of objects

Inside the `response` parameter, there is a list with a franchisee as the key and an array with a list of locations of this franchisee as the value. Each array object contains the following values:

Parameter | Description
--------- | -----------
spot_id | Location ID
spot_name | Location name
spot_adress | Location address

