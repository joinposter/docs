## storage.deleteWriteOff: Удаление списания

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/storage.deleteWriteOff'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$delete = [
    'write_off_id' => 60
];

$data = sendRequest($url, 'post', $delete);
```

> Пример ответа:

```json
{
  "success":1
}
```

Метод удаляет списание

### HTTP запрос

`POST https://joinposter.com/api/storage.deleteWriteOff`

### POST-параметры запроса storage.deleteWriteOff

Параметр | Описание
-------- | --------
write_off_id | id списания для удаления

### Параметры ответа storage.deleteWriteOff

Параметр | Описание
-------- | --------
success | Статус выполнения операции: 1 — успешно, 0 — нет
