## settings.getLogo: Логотип компании

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/settings.getLogo'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Пример ответа:

```json
{
  "response":{
    "value":"\/upload\/4\/icon.png"
  }
}
```

Метод возвращает логотип компании

### HTTP запрос

`POST https://joinposter.com/api/settings.getLogo`

### Параметры ответа settings.getLogo

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит объект, внутри которого есть следующий параметр:

Параметр | Описание
-------- | --------
value | Ссылка на логотип компании. Логотип хранится на домене `https://joinposter.com`.
