## storage.createMoving: Create a Transfer

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/storage.createMoving'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$moving = [
    "moving" => [
        "date"          => "2015-11-18 22:35:54",
        "from_storage"  => "1",
        "to_storage"    => "2",
        "comment"       => "Comment for moving"
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
  "response":5
}
```

The method creates a transfer

### HTTP request

`POST https://joinposter.com/api/storage.createMoving`

### POST parameters of the storage.createMoving request

Parameter | Description
--------- | -----------
date | Waste date and time in the `Ymd` format
from_storage_id | The ID of a storage a transfer is made from
to_storage_id | The ID of a storage a transfer is made to
comment | An optional parameter, comment for transfer 
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

### The storage.createMoving response parameters

Parameter | Description
--------- | -----------
success | The operation status: 1—successful, 0—unsuccessful
response | Created transfer ID

