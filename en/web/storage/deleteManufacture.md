## storage.deleteManufacture: Remove Manufacture

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/storage.deleteManufacture'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$delete = [
    'manufacture_id' => 1
];

$data = sendRequest($url, 'post', $delete);
```

> Response example:

```json
{
  "response":true
}
```

The method removes a manufacture

### HTTP request

`POST https://joinposter.com/api/storage.deleteManufacture`

### POST parameters of the storage.deleteManufacture

Parameter | Description
-------- | --------
manufacture_id | ID of the manufacture for removal 

### The storage.deleteManufacture response parameters

Parameter | Description
-------- | --------
response | The result of the removing of manufacture, `true` — yes, `false` — no

