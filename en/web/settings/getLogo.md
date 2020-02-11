## settings.getLogo: Company Logo

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/settings.getLogo'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response":{
    "value":"\/upload\/4\/icon.png"
  }
}
```

The method returns the company logo

### HTTP request

`POST https://joinposter.com/api/settings.getLogo`

### The settings.getLogo response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameter:

Parameter | Description
--------- | -----------
value | Link to the company logo. The logo is stored at the `https://joinposter.com` domain

