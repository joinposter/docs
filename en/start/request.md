## Sending requests

>  Example of request:

```php
<?php
function sendRequest($url, $type = 'get', $params = [], $json = false)
{
    $ch = curl_init();
    curl_setopt($ch, CURLOPT_URL, $url);
    curl_setopt($ch, CURLOPT_HEADER, false);
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
    curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
    curl_setopt($ch, CURLOPT_SSL_VERIFYHOST, false);

    if ($type == 'post' || $type == 'put') {
        curl_setopt($ch, CURLOPT_POST, true);

        if ($json) {
            $params = json_encode($params);

            curl_setopt($ch, CURLOPT_HTTPHEADER, [
                'Content-Type: application/json',
                'Content-Length: ' . strlen($params)
            ]);

            curl_setopt($ch, CURLOPT_POSTFIELDS, $params);
        } else {
            curl_setopt($ch, CURLOPT_POSTFIELDS, http_build_query($params));
        }
    }

    curl_setopt($ch, CURLOPT_CONNECTTIMEOUT, 30);
    curl_setopt($ch, CURLOPT_USERAGENT, 'Poster (http://joinposter.com)');

    $data = curl_exec($ch);
    curl_close($ch);

    return $data;
}

$url = 'https://joinposter.com/api/clients.getGroup' 
    . '?format=json'
    . '&token=687409:4164553abf6a031302898da7800b59fb'
    . '&group_id=1';

$group = sendRequest($url);
```

> Example of response:

```json
{
   "response":{
      "client_groups_id":"1",
      "client_groups_name":"Favourite customer",
      "loyalty_type":"1",
      "client_groups_discount":"10",
      "birthday_bonus":"5000",
      "count_groups_clients":"125"
   }
}
```

> Example of error:

```json
{
   "error":{
      "code":11,
      "message":"Bad access token"
   }
}
```

Data is exchanged with Poster using GET or POST https requests

<aside class="info">
    Almost all requests to web API, requires access token, which transfered as GET parameter. 
    Exceceptions are only methods for authorization.
</aside> 

### General address format for all https requests

`https://joinposter.com/api/{method}?format={format}&token={token}&param1=val1&param2=val2`

### Address parameters for all https requests

Parameter | Description
--------- | -----------
method | The name of the API method, for example, clients.getGroups
token | Authorization token. To receive this token you will have to implement [authorization process](/en/docs/v3/start/authApi).
format | An optional parameter indicating the response format. It can be xml or json. The default format is json.
param, val | Extra parameter names and values, this parameters are individual for 

The response comes in the specified format and contains a top-level `error` or `response` object. 
The error object is specified with code and message parameters. 
You can find a list of error descriptions in a [table](/en/docs/v3/web/errors).
