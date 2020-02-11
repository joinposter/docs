## menu.removeDish: Remove a Dish

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/menu.removeDish'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$dish = [
    'dish_id' => 925,
];

$data = sendRequest($url, 'post', $dish);
```

> Response example:

```json
{  
  "response":true
}
```

The method removes a dish

### HTTP request

`GET https://joinposter.com/api/menu.removeDish`

### POST parameters of the menu.removeDish request

Parameter | Description
--------- | -----------
dish_id | Dish ID

### The menu.removeDish response parameters

Parameter | Description
--------- | -----------
response | true if a dish has been successfully removed

