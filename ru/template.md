## <method>: <description>

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/<method>'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$group = [
];

$data = sendRequest($url, 'post', $group);

```

> Пример ответа:

```json
{
  "response":6
}
```

<description>

### HTTP запрос

`POST https://joinposter.com/api/<method>`

### POST-параметры запроса <method>

Параметр | Описание
-------- | --------
id | Id группы 

### Параметры ответа <method>

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит объект, внутри которого есть следующие параметры:
