## storage.getPacks: List of Packs

> Request example:

```php
<?
$url = 'https://joinposter.com/api/storage.getPacks' 
  . '?format=json'
  . '&token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response":[
    {
      "pack_id":"1",
      "name":"",
      "unit":"p",
      "count":"0.0000",
      "type":"0"
    },
    {
      "pack_id":"2",
      "name":"",
      "unit":"l",
      "count":"0.0000",
      "type":"0"
    },
    {
      "pack_id":"3",
      "name":"",
      "unit":"kg",
      "count":"0.0000",
      "type":"0"
    },
    {
      "pack_id":"5",
      "name":"Milk pack",
      "unit":"p",
      "count":"20.0000",
      "type":"1"
    },
    {
      "pack_id":"6",
      "name":"Water",
      "unit":"l",
      "count":"20.0000",
      "type":"1"
    }
  ]
}
```

The request for a list of all packs.

### HTTP request

`GET https://joinposter.com/api/storage.getPacks`

### The storage.getPacks response parameters

Parameter | Description
--------- | -----------
pack_id | Pack ID
name | Pack name
unit | Unit: kg—kg, p—pcs, l—l
count | Count in pieces, kg, or liters
type | Pack type: 0—basic, 1—custom

