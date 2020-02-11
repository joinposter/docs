## settings.getLanguage: Язык аккаунта

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/settings.getLanguage'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Пример ответа:

```json
{
  "response":{
    "value":"ru"
  }
}
```

Метод возвращает язык аккаунта

### HTTP запрос

`POST https://joinposter.com/api/settings.getLanguage`


### Параметры ответа settings.getLanguage

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит объект, внутри которого есть следующий параметр:

Параметр | Описание
-------- | --------
value | Строка с языком аккаунта, в формате ISO 639. Украинский язык обозначается как `ua`.
