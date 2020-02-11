## access.updateTablet: Изменение свойств терминала

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/access.updateTablet'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$tablet = [
    'spot_tablet_id'   => 2,
    'spot_id'          => 1,
    'spot_tablet_name' => 'Новый терминал',
    'spot_code'        => 'b3ss7m1p',
];

$data = sendRequest($url, 'post', $tablet);
```

> Пример ответа:

```json
{  
  "response":2
}
```

Метод изменяет свойства терминала

### HTTP POST запрос

`https://joinposter.com/api/access.updateTablet`

### POST-параметры запроса access.updateTablet

Параметр | Описание
-------- | --------
spot_tablet_id | Id терминала
spot_id | Id заведения к которому относится терминал
spot_tablet_name | Название терминала
spot_code | Пароль терминала

### Параметры ответа access.updateTablet

Параметр | Описание
-------- | --------
response | Id изменённого терминала
