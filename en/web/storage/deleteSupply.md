## storage.deleteSupply: Remove Supply

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/storage.deleteSupply'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$delete = [
    'supply_id' => 7
];

$data = sendRequest($url, 'post', $delete);
```

> Response example:

```json
{
  "success":1
}
```

The method removes a supply

### HTTP request

`POST https://joinposter.com/api/storage.deleteSupply`

### POST parameters of the storage.deleteSupply request

Parameter | Description
--------- | -----------
supply_id | The ID of the supply for removal

### The storage.deleteSupply response parameters

Parameter | Description
--------- | -----------
success | The operation status: 1—successful, 0—unsuccessful

