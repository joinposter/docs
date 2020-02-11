## settings.getTimeZones: Account Time Zone

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/settings.getTimeZones'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response":{
    "value":"Europe\/Kiev"
  }
}
```

The method returns the account time zone

### HTTP request

`POST https://joinposter.com/api/settings.getTimeZones`

### The settings.getTimeZones response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameter:

Parameter | Description
--------- | -----------
value | The account time zone line

