## settings.getCompanyName: Account Name

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/settings.getCompanyName'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response":{
    "value":"Демо-версия Poster"
  }
}
```

The method returns the account name

### HTTP request

`POST https://joinposter.com/api/settings.getCompanyName`

### The settings.getCompanyName response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameter:

Parameter | Description
--------- | -----------
value | A line with the account name

