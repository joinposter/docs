## storage.updateManufacture: Update Manufacture Data

> Request example:

```php
<?
$url = 'https://joinposter.com/api/storage.updateManufacture?' .
  'format=json&token=687409:4164553abf6a031302898da7800b59fb';

$manufacture = [
    "manufacture_id"  => 7,
    "date"            => "2016-12-21 12:12:54",
    "storage_id"      => 1,
    "products" => [
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

$manufacture_id = sendRequest($url, 'post', $manufacture, true);
```

> Response example:

```json
{
  "response":6
}
```

The request allows updating the existing manufacture data.

### HTTP request

`POST https://joinposter.com/api/storage.updateManufacture`

### POST parameters of the storage.updateManufacture request

Parameter | Description
--------- | -----------
manufacture_id | The ID of the manufacture being updated
date | Manufacture date
storage_id | Storage ID
products | List of dishes / semi-finished products included in the manufacture

### The products parameter entry

The word “entity” means a dish or a semi-finished product. When the entity is manufactured for the first time, it gets a unique ingredient_id to get its inventory in storage by.

Parameter | Description
--------- | -----------
id | Entity ID
num | Count (in pcs/kg)
type | Type of entity: 1—semi-finished product, 2—dish

### The storage.updateManufacture response parameters

Parameter | Description
--------- | -----------
response | The edited manufacture ID

