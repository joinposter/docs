## menu.removePrepack: Удаление полуфабриката

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.removePrepack'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$prepack = [
    'prepack_id' => 177,
];

$data = sendRequest($url, 'post', $prepack);
```

> Пример ответа:

```json
{  
  "response":true
}
```

Метод удаляет полуфабрикат

### HTTP запрос

`GET https://joinposter.com/api/menu.removePrepack`

### POST-параметры запроса menu.removePrepack

Параметр | Описание
-------- | --------
prepack_id | Id полуфабриката

### Параметры ответа menu.removePrepack

Параметр | Описание
-------- | --------
response | true, если полуфабрикат успешно удалён
