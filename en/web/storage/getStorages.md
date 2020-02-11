## storage.getStorages: Get All Storages

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/storage.getStorages'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response":[
    {
      "storage_id":"1",
      "storage_name":"Склад Кухня",
      "storage_adress":"",
      "delete":"0"
    },
    {
      "storage_id":"2",
      "storage_name":"Склад Бар",
      "storage_adress":"",
      "delete":"0"
    }
  ]
}
```

The method returns all storages

### HTTP request

`GET https://joinposter.com/api/storage.getStorages`

### The storage.getStorages response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an array, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
storage_id | Storage ID
storage_name | Storage name
storage_adress | Storage address
delete | The status of a storage removed: 1—removed, 0—not removed

