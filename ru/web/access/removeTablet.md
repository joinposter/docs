## access.removeTablet: Удаление терминала

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/access.removeTablet'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$tablet = [
    'spot_tablet_id' => 1,
];

$data = sendRequest($url, 'post', $tablet);
```

> Пример ответа:

```json
{  
  "response":true
}
```

Метод удаляет терминал

### HTTP POST запрос

`https://joinposter.com/api/access.removeTablet`

### POST-параметры запроса access.removeTablet

Параметр | Описание
-------- | --------
spot_tablet_id | Id удаляемого терминала 

### Параметры ответа access.removeTablet

Параметр | Описание
-------- | --------
response | `true`, если терминал успешно удален
