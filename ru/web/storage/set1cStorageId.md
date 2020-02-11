## storage.set1cStorageId: Изменение id складов в системе 1С

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/storage.set1cStorageId'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$storage = [
    'id' => [
        [
            'storage_id' => 32,
            'id_1c'   => 'b80ffc81-0fc9-11e7-9ab4-ace01035e460',
        ],
    ],
];

$data = sendRequest($url, 'post', $storage);
```

> Пример ответа:

```json
{  
  "success":1
}
```

Метод изменяет id складов в системе 1С

### HTTP запрос

`GET https://joinposter.com/api/storage.set1cStorageId`

### POST-параметры запроса storage.set1cStorageId

Параметр | Описание
-------- | --------
id | Массив объектов

В свою очередь, каждый объект должен содержать следующие свойства:

Параметр | Описание
-------- | --------
storage_id | Id складов
id_1c | Id складов в системе 1С

### Параметры ответа storage.set1cStorageId

Параметр | Описание
-------- | --------
success | 1, если id складов в системе 1С успешно изменены
