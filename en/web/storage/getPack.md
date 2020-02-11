## storage.getPack: Get a Pack

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/storage.getPack' 
  . '?format=json'
  . '&token=687409:4164553abf6a031302898da7800b59fb'
  . '&pack_id=4';

$data = sendRequest($url);
```
> Response example:

```json
{
  "response":{
    "pack_id":"5",
    "name":"Пак молока",
    "unit":"p",
    "count":"20.0000",
    "type":"1"
  }
}
```

The method returns the specific pack data.

### HTTP request

`GET https://joinposter.com/api/storage.getPack`

### GET parameters of the storage.getPack request

Parameter | Description
--------- | -----------
pack_id | The ID of a pack to return the detailed data for

### The storage.getPack response parameters

Parameter | Description
--------- | -----------
pack_id | Pack ID
name | Pack name
unit | Unit: kg—kg, p—pcs, l—l
count | Count in pieces, kg, or liters
type | Pack type: 0—basic, 1—custom

