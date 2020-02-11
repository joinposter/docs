## settings.getTimeZones: Часовой пояс аккаунта

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/settings.getTimeZones'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Пример ответа:

```json
{
  "response":{
    "value":"Europe\/Kiev"
  }
}
```

Метод возвращает часовой пояс аккаунта

### HTTP запрос

`POST https://joinposter.com/api/settings.getTimeZones`

### Параметры ответа settings.getTimeZones

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит объект, внутри которого есть следующий параметр:

Параметр | Описание
-------- | --------
value | Строка с часовым поясом аккаунта 
