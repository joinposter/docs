## clients.removeClients: Удаление пачки клиентов

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/clients.removeClients'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$client = [
    'ids' => [1, 2],
];

$data = sendRequest($url, 'post', $client);
```

> Пример ответа:

```json
{  
  "response":[1,2]
}
```

Метод удаляет несколько клиентов

### HTTP запрос

`GET https://joinposter.com/api/clients.removeClients`

### POST-параметры запроса clients.removeClients

Параметр | Описание
-------- | --------
ids | Массив Id клиентов

### Параметры ответа clients.removeClients

Параметр | Описание
-------- | --------
response | Массив id удаленных клиентов
