## storage.createSupply: Create Supply

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/storage.createSupply'
    . '?token=687409:4164553abf6a031302898da7800b59fb';

$supply = [
    "supply" => [
        "supplier_id"   => "1",
        "storage_id"    => "1",
        "date"          => date("Y-m-d H:i:s"),
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

$data = sendRequest($url, 'post', $supply);
```

> Response example:

```json
{
  "success":1,
  "response":7
}
```

The method creates a supply

### HTTP request

`POST https://joinposter.com/api/storage.createSupply`

### POST parameters of the storage.createSupply request

Object `supply` contains the following parameters

Parameter | Description
--------- | -----------
date | Supply date in the `Y-m-d H:i:s` format
supplier_id | Supplier ID
storage_id | The ID of the storage the supply is made to
supply_comment | Comment to supply
account_id | An optional parameter, the account ID in the accounting department the supply is attached to
ingredient | Object array for supply

Each object of the `ingredient` array contains the following parameters

Parameter | Description
--------- | -----------
id | The ID of an ingredient, product, or a product modifier
type | Type of the wasted object: product—1, ingredient—4, product modifier—5
num | The wasted ingredient count
sum | The cost per unit in hryvnias/rubles
packing | An optional parameter, the pack ID

### storage.createSupply response parameters

Parameter | Description
--------- | -----------
success | The operation status: 1—successful, 0—unsuccessful
response | Created transfer ID

