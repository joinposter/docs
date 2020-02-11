## clients.removeGroup: Удаление группы клиентов

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/clients.removeGroup?'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$group = [
  'group_id' => 6,
];

$data = sendRequest($url, 'post', $group);
```

> Пример ответа:

```json
{
  "response":true
}
```

Метод удаляет группу клиентов

!> Удаленные данные восстановлению не подлежат!

### HTTP запрос

`POST https://joinposter.com/api/clients.removeGroup`

### POST-параметры запроса clients.removeGroup

Параметр | Описание
-------- | --------
group_id | Id группы клиентов

### Параметры ответа clients.removeGroup

Параметр | Описание
-------- | --------
response | true, если группа клиентов успешно удалена

