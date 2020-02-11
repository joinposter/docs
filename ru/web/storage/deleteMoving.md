## storage.deleteMoving: Удаление перемещения

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/storage.deleteMoving'
    . '?token=687409:4164553abf6a031302898da7800b59fb';

$delete = [
    'moving_id' => 7
];

$data = sendRequest($url, 'post', $delete);
```

> Пример ответа:

```json
{
  "success":1
}
```

Метод удаляет перемещение

### HTTP запрос

`POST https://joinposter.com/api/storage.deleteMoving`

### POST-параметры запроса storage.deleteMoving

Параметр | Описание
-------- | --------
moving_id | id перемещения для удаления

### Параметры ответа storage.deleteMoving

Параметр | Описание
-------- | --------
success | Статус выполнения операции: 1 — успешно, 0 — нет
