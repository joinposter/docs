## settings.getCompanyType: Location Type

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/settings.getCompanyType'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response":{
    "value":"1"
  }
}
```

The method returns the location type

### HTTP request

`POST https://joinposter.com/api/settings.getCompanyType`

### The settings.getCompanyType response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameter:

Parameter | Description
--------- | -----------
value | The status of the location type: 1—cafe, 2—store

