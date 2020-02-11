## storage.updateMoving: Update a Transfer

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/storage.updateMoving'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$moving = [
    "moving" => [
        "moving_id"     => "16",
        "date"          => "2015-11-18 22:35:54",
        "from_storage"  => "1",
        "to_storage"    => "2"
    ],
    "ingredient" => [
        [
            "id"        => "138",
            "type"      => "1",
            "num"       => "3",
            "sum"       => "6",
        ]
    ]
];

$data = sendRequest($url, 'post', $moving);
```

> Response example:

```json
{
  "success":1,
  "response":16
}
```

The method updates a transfer

### HTTP request

`POST https://joinposter.com/api/storage.updateMoving`

### POST parameters of the storage.updateMoving request

Parameter | Description
--------- | -----------
moving_id | The transfer ID that is edited
date | Waste date and time in the `Ymd` format
from_storage_id | The ID of a storage a transfer is made from
to_storage_id | The ID of a storage a transfer is made to
ingredient | Object array for transfer

Each object of the `ingredient` array contains the following parameters

Parameter | Description
--------- | -----------
id | The ID of an ingredient, product, or a product modifier
type | Type of the wasted object: product—1, ingredient—4, product modifier—5
num | The wasted ingredient count
reason | An optional parameter, a reason for waste
packing | An optional parameter, the pack ID
sum | The cost per unit in hryvnias/rubles

### storage.updateMoving response parameters

Parameter | Description
--------- | -----------
success | The operation status: 1—successful, 0—unsuccessful
response | Updated transfer ID

