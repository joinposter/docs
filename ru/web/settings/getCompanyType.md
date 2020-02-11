## settings.getCompanyType: Тип заведения

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/settings.getCompanyType'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Пример ответа:

```json
{
  "response":{
    "value":"1"
  }
}
```

Метод возвращает тип заведения

### HTTP запрос

`POST https://joinposter.com/api/settings.getCompanyType`

### Параметры ответа settings.getCompanyType

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит объект, внутри которого есть следующий параметр:

Параметр | Описание
-------- | --------
value | Признак типа заведения: 1 — кафе, 2 — магазин 
