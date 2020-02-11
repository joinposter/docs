## storage.deleteWriteOff: Remove a Waste

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/storage.deleteWriteOff'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$delete = [
    'write_off_id' => 60
];

$data = sendRequest($url, 'post', $delete);
```

> Response example:

```json
{
  "success":1
}
```

The method removes a waste

### HTTP request

`POST https://joinposter.com/api/storage.deleteWriteOff`

### POST parameters of the storage.deleteWriteOff request

Parameter | Description
--------- | -----------
write_off_id | The ID of the waste for removal

### The storage.deleteWriteOff response parameters

Parameter | Description
--------- | -----------
success | The operation status: 1—successful, 0—unsuccessful

