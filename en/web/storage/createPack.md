## storage.createPack: Create a Pack

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/storage.createPack'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$pack = [
    'name' => 'Ящик',
    'unit' => 'kg',
    'count' => 0.5,
];

$data = sendRequest($url, 'post', $pack);
```

> Request example:

```cURL
curl --location --request POST 'https://joinposter.com/api/storage.createPack?token=687409:4164553abf6a031302898da7800b59fb' \
--header 'Content-Type: application/json' \
--data-raw '{
  "name": "Ящик",
  "unit": "kg",
  "count": 0.5
}'
```

> Response example:

```json
{  
  "response": 5
}
```

The method creates a pack

### HTTP POST request

`POST https://joinposter.com/api/storage.createPack`

### POST parameters of the storage.createPack request

Parameter | Description
-------- | --------
name | Pack name
unit | Unit: kg — kg, p — pcs, l — l
count | Count in pieces, kg or liters

### Параметры ответа storage.createPack

Parameter | Description
-------- | --------
response | The created pack ID
