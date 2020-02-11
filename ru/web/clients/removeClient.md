## clients.removeClient: Удаление клиента

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/clients.removeClient'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$client = [
    'client_id' => 2,
];

$data = sendRequest($url, 'post', $client);
```

> Пример ответа:

```json
{  
  "response":true
}
```

Метод удаляет клиента

### HTTP запрос

`GET https://joinposter.com/api/clients.removeClient`

### POST-параметры запроса clients.removeClient

Параметр | Описание
-------- | --------
client_id | Id клиента

### Параметры ответа clients.removeClient

Параметр | Описание
-------- | --------
response | true, если клиент успешно удалён
