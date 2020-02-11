## storage.deleteManufacture: Удаление производства 

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/storage.deleteManufacture'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$delete = [
    'manufacture_id' => 1
];

$data = sendRequest($url, 'post', $delete);
```

> Пример ответа:

```json
{
  "response":true
}
```

Метод удаляет производство

### HTTP запрос

`POST https://joinposter.com/api/storage.deleteManufacture`

### POST-параметры запроса storage.deleteManufacture

Параметр | Описание
-------- | --------
manufacture_id | Id производства для удаления 

### Параметры ответа storage.deleteManufacture

Параметр | Описание
-------- | --------
response | Результат удаления производства, `true` — удалено, `false` — нет

