## makeRequest: Make a Cross Domain Request


<details open>
<summary>Request example</summary>

```javascript
    Poster.makeRequest('http://mywebsite.com', {
        headers: [
            'Content-Type: application/json'            
        ],
        method: 'post',
        data: { foo: 'bar' },
        timeout: 10000
    }, (answer) => {
        if (answer && Number(answer.code) === 200) {
            console.log(answer.result);
        }
    });
```

</details>

The method makes HTTP requests to any remote URL. Requests are proxied through the Poster backend

### Arguments

Argument | Description
-------- | -----------
1st, url | Remote resource URL
2nd, options | An object with request settings
3rd, callback | Response handler function

Object `options` has such parameters:

Parameter | Description
--------- | -----------
headers | Optional parameter, array of headers which have to be send in the request
method | Request type: `get`, `post`, `put`, `delete`. `get` by default.
data | Request body, send only in `post` and `put` requests. To send GET-parameter, just pass right away in the URL   
timeout | Optional parameter, maximum request execution time in milliseconds. By default request has no timeout.
localRequest | Optional parameter, send `true` if you want to make a request to device in local network. `false` by default. 


### Response

In `callback`, first argument is an object with response from the server. It has 

Parameter | Description
--------- | -----------
result | Response body, `false` — if request failed 
code | HTTP-status of response. Returns: `0` – if request failed by timeout, `1` — if response contains invalid JSON.


### Signature

If you are working with vulnerable transactions such as payment, points writing-off or accrual, your application needs confirmation that the request has come from a reliable source. For this, a request signature is used. The `Poster.makeRequest` method proxies requests via the Poster server, where a request is signed and sent to your server.

The request is signed through the following algorithm. In turn, there concatenate:

1. Full request link together with GET parameters.
2. JSON line created from the request body; if GET is the request, the body is excluded from signing.
3. The request sending time; it is transmitted in the `X-Poster-Time` header in the Unix Timestamp format.
4. Application secret, which is a key that you received when you registered your application.

The resulting line is hashed by the md5 method and sent along with the request in the `X-Poster-Signature` header.

For your convenience, each request has the following headings attached:

- `X-Poster-Url` — account name 
- `X-Poster-Spot-Id` — the ID of the location the request has been sent from
- `X-Poster-Tablet-Id` — the ID of the register the request has been sent from


<details open>
<summary>Function which checks signature</summary>

<!-- tabs:start -->

#### ** JS **

```javascript
var md5 = require('md5');

function checkSign(url, headers, body, secret) {
    var signStr = url + (body ? JSON.stringify(body) : "") + headers['x-poster-time'] + secret;
    var signature = md5(signStr);

    return signature === headers['x-poster-signature'];
}
```

#### ** PHP **

```php
<?php

function checkSign($url, $headers, $body, $secret) {
    $signatureStr = $url . ($body ? json_encode($body) : "") . $headers['X-Poster-Time'] . $secret;
    $signature = md5($signatureStr);
    
    return $headers['X-Poster-Signature'] == $signature;
}
```

<!-- tabs:end -->

</details>

