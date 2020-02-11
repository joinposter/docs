## storage.updateWriteOff: Update a Waste

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/storage.updateWriteOff'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$writeOff = [
    "write_off" => [
        "id"  => "56",
        "storage_id"    => "1",
        "date"          => date("Y-m-d H:i:s"),
    ],
    "ingredient" => [
        [
            "id"        => "138",
            "type"      => "1",
            "weight"    => "3",
            "sum"       => "6",
        ]
    ]
];

$data = sendRequest($url, 'post', $writeOff);
```

> Response example:

```json
{
  "success":1,
  "response":56
}
```

The method updates a waste

### HTTP request

`POST https://joinposter.com/api/storage.updateWriteOff`

### POST parameters of the storage.updateWriteOff request

Parameter | Description
--------- | -----------
id | Edited waste ID
date | Supply date in the `Y-m-d H:i:s` format. The date must be in the inventory check period in which the waste has been made.
storage_id | Waste storage ID
ingredient | Waste object array
reason_id | An optional parameter, id reason of waste

Each object of the `ingredient` array contains the following parameters

Parameter | Description
--------- | -----------
id | The ID of an ingredient, product, or a product modifier
type | Type of the wasted object: product—1, dish — 2, prepack — 3, ingredient—4, product modifier—5
weight | The wasted ingredient count
sum | The cost per unit in hryvnias/rubles
packing | An optional parameter, the pack ID
reason | An optional parameter, comment for ingredient write-off

### The storage.updateWriteOff response parameters

Parameter | Description
--------- | -----------
success | The operation status: 1—successful, 0—unsuccessful
response | Updated waste ID

