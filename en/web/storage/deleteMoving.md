## storage.deleteMoving: Remove a Transfer

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/storage.deleteMoving'
    . '?token=687409:4164553abf6a031302898da7800b59fb';

$delete = [
    'moving_id' => 7
];

$data = sendRequest($url, 'post', $delete);
```

> Response example:

```json
{
  "success":1
}
```

The method removes a transfer

### HTTP request

`POST https://joinposter.com/api/storage.deleteMoving`

### POST parameters of the storage.deleteMoving request

Parameter | Description
--------- | -----------
moving_id | The ID of the transfer for removal

### The storage.deleteMoving response parameters

Parameter | Description
--------- | -----------
success | The operation status: 1—successful, 0—unsuccessful

