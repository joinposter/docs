## access.createTablet: Создание терминала

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/access.createTablet'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$tablet = [
    'spot_id'          => 1,
    'spot_tablet_name' => 'Новый терминал',
    'spot_code'        => 'crsa5a54',
];

$data = sendRequest($url, 'post', $tablet);
```

> Пример ответа:

```json
{  
  "response":2
}
```

Метод создаёт терминал

### HTTP POST запрос

`https://joinposter.com/api/access.createTablet`

### POST-параметры запроса access.createTablet

Параметр | Описание
-------- | --------
spot_id | Id заведения к которому будет относиться терминал
spot_tablet_name | Название терминала
spot_code | Пароль терминала

### Параметры ответа access.createTablet

Параметр | Описание
-------- | --------
response | Id созданного терминала
