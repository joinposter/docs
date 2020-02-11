## menu.removePrepack: Remove a Semi-Finished Product

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.removePrepack'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$prepack = [
    'prepack_id' => 177,
];

$data = sendRequest($url, 'post', $prepack);
```

> Response example:

```json
{  
  "response":true
}
```

The method removes a semi-finished product

### HTTP request

`GET https://joinposter.com/api/menu.removePrepack`

### POST parameters of the menu.removePrepack request

Parameter | Description
--------- | -----------
prepack_id | Semi-finished product ID

### The menu.removePrepack response parameters

Parameter | Description
--------- | -----------
response | true if the semi-finished product has been successfully removed

