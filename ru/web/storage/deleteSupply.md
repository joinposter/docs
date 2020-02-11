## storage.deleteSupply: Удаление поставки 

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/storage.deleteSupply'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$delete = [
    'supply_id' => 7
];

$data = sendRequest($url, 'post', $delete);
```

> Пример ответа:

```json
{
  "success":1
}
```

Метод удаляет поставку

### HTTP запрос

`POST https://joinposter.com/api/storage.deleteSupply`

### POST-параметры запроса storage.deleteSupply

Параметр | Описание
-------- | --------
supply_id | id поставки для удаления 

### Параметры ответа storage.deleteSupply

Параметр | Описание
-------- | --------
success | Статус выполнения операции: 1 — успешно, 0 — нет
