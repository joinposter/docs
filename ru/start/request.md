## Отправка запросов

>  Пример запроса:

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

> Пример ответа:

```json
{
   "response":{
      "client_groups_id":"1",
      "client_groups_name":"Постоянный посетитель",
      "loyalty_type":"1",
      "client_groups_discount":"10",
      "birthday_bonus":"5000",
      "count_groups_clients":"125"
   }
}
```

> Пример ошибки:

```json
{
   "error":{
      "code":11,
      "message":"Bad access token"
   }
}
```

Обмен данных с Poster происходит с помощью GET или POST https-запросов. 

!> Все запросы к Web API, авторизуются при помощи токена, который передается как GET параметр. Исключением являются только запросы на авторизацию. 

### Общий формат адреса для всех https-запросов

`https://joinposter.com/api/{method}?format={format}&token={token}&param1=val1&param2=val2`

### Параметры адреса для всех https-запросов

Параметр | Описание
-------- | --------
method | Название метода API, например, clients.getGroups
token | Авторизационный токен. Чтобы получить токен, пройдите один из [способов авторизации](/docs/v3/start/authApi).
format | Формат запроса, доступные значения: json или xml 
param1, val1 | Дополнительные параметры которые зависят от запроса 

 
Ответ приходит в указанном формате и содержит объект верхнего уровня `error` либо `response`. 
Объект `error` уточняется параметрами code и message. 
Со списком всех ошибок вы можете ознакомиться в [таблице ошибок](/docs/v3/web/errors).
