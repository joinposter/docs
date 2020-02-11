## storage.updateSupply: Update Supply

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/storage.updateSupply'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$supply = [
    "supply" => [
        "supply_id"     => "51",
        "supplier_id"   => "1",
        "storage_id"    => "1",
        "date"          => date("Y-m-d H:i:s"),
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
  "response":"51"
}
```

The method updates a supply

### HTTP request

`POST https://joinposter.com/api/storage.updateSupply`

### POST parameters of the storage.updateSupply request

Parameter | Description
--------- | -----------
supply_id | The edited supply ID
date | Supply date in the `Y-m-d H:i:s` format
supplier_id | Supplier ID
storage_id | A mandatory parameter, the ID of the storage the supply is made to
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

### The storage.updateSupply response parameters

Parameter | Description
--------- | -----------
success | The operation status: 1—successful, 0—unsuccessful
response | The updated supply ID

