## settings.getCompanyName: Название аккаунта

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/settings.getCompanyName'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Пример ответа:

```json
{
  "response":{
    "value":"Демо-версия Poster"
  }
}
```

Метод возвращает название аккаунта

### HTTP запрос

`POST https://joinposter.com/api/settings.getCompanyName`

### Параметры ответа settings.getCompanyName

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит объект, внутри которого есть следующий параметр:

Параметр | Описание
-------- | --------
value | Строка с названием аккаунта
