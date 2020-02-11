## settings.changeSettings: Update Properties of Customer Account Settings

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/settings.changeSettings'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$settings = [
    'uses_taxes'              => 1,
    'uses_cash_shifts'        => 0,
    'uses_fiscality'          => 0,
    'print_fiscal_by_default' => 0,
    'timezones'               => 'Europe/Moscow',
];

$data = sendRequest($url, 'post', $settings);
```

> Response example:

```json
{  
  "response":true
}
```

The method changes the properties of the customer account settings

### HTTP POST request

`https://joinposter.com/api/settings.changeSettings`

### POST parameters of the settings.changeSettings request

Parameter | Description
--------- | -----------
uses_taxes | The status of using taxes: 0—not to use, 1—to use. By default, it is not transmitted.
uses_cash_shifts | The status of using register shifts: 0—not to use, 1—to use. By default, it is not transmitted.
uses_fiscality | The status of using fiscalization: 0—not to use, 1—to use. By default, it is not transmitted.
print_fiscal_by_default | The status of printing a fiscal receipt by default: 0—not to print, 1—to print. By default, it is not transmitted.
timezones | Time zone. By default, it is not transmitted.

### The settings.changeSettings response parameters

Parameter | Description
--------- | -----------
response | true if the customer account settings properties have been successfully updated

