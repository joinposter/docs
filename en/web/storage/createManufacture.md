## storage.createManufacture: Create a Manufacture

> Request example:

```php
<?
$url = 'https://joinposter.com/api/storage.createManufacture' 
  . '?format=json'
  . '&token=687409:4164553abf6a031302898da7800b59fb';

$manufacture = [
    "date"          => "2016-12-21 11:12:54",
    "storage_id"    => 1,
    "products"      => [
        [
            "id"    => 64,
            "type"  => 1,
            "num"   => 3
        ],
        [
            "id"    => 65,
            "type"  => 1,
            "num"   => 25
        ],
    ]
];

$data = sendRequest($url, 'post', $manufacture, true);
```

> Response example:

```json
{
  "response":6
}
```

The request creates a manufacture of dishes and semi-finished products

### HTTP request

`POST https://joinposter.com/api/storage.createManufacture`

### POST parameters of the storage.createManufacture request

Parameter | Description
--------- | -----------
date | Manufacture date
storage_id | Storage ID
products | List of dishes or semi-finished products included in the manufacture

### The products parameter entry

The word “entity” means a dish or a semi-finished product. When the entity is manufactured for the first time, it gets a unique ingredient_id to get its inventory in storage by.

Parameter | Description
--------- | -----------
id | Entity ID
num | Count in pcs or kg
type | Type of entity: 1—semi-finished product, 2—dish

### The storage.createManufacture response parameters

Parameter | Description
--------- | -----------
response | The created manufacture ID

