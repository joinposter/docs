## clients.set1cClientId: Изменение id клиента в системе 1С

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/clients.set1cClientId'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$client = [
    'id' => [
        [
            'client_id' => 38,
            'id_1c'     => 'b80ffc81-0fc9-11e7-9ab4-ace01035e460',
        ],
    ],
];

$data = sendRequest($url, 'post', $client);
```

> Пример ответа:

```json
{  
  "success":1
}
```

Метод изменяет id клиента в системе 1С

### HTTP запрос

`GET https://joinposter.com/api/clients.set1cClientId`

### POST-параметры запроса clients.set1cClientId

Параметр | Описание
-------- | --------
id | Массив объектов

В свою очередь, каждый объект должен содержать следующие свойства:

Параметр | Описание
-------- | --------
client_id | Id клиента
id_1c | Id клиента в системе 1С

### Параметры ответа clients.set1cClientId

Параметр | Описание
-------- | --------
success | 1, если id клиента в системе 1С успешно изменён
