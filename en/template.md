## <method>: <description>

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/<method>'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$group = [
];

$data = PosterAPI::sendRequest($url, 'post', $group);

```

> Response example:

```json
{
  "response":6
}
```

<description>

### HTTP request

`POST https://joinposter.com/api/<method>`

### Request GET-params for <method>

Parameter | Description
--------- | -----------

### Request POST-params for <method>

Parameter | Description
--------- | -----------
id | Group Id 

### Response from <method>

Parameter | Description
--------- | -----------
response | Response result object

`response` contains object with next params:  
