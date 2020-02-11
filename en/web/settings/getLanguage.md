## settings.getLanguage: Account Language

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/settings.getLanguage'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response":{
    "value":"ru"
  }
}
```

The method returns the account language

### HTTP request

`POST https://joinposter.com/api/settings.getLanguage`

### The settings.getLanguage response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameter:

Parameter | Description
--------- | -----------
value | The account language line in the ISO 639 format. The Ukrainian language is designated as `ua`.

