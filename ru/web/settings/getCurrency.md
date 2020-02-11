## settings.getCurrency: Валюта аккаунта

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/settings.getCurrency'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Пример ответа:

```json
{  
  "response":{  
    "currency_id":"2",
    "currency_name":"Рубль",
    "currency_code":"руб.",
    "currency_symbol":"<i class=\"icon-rouble\"><\/i>",
    "currency_code_iso":"RUB"
  }
}
```

Метод возвращает валюту аккаунта

### HTTP запрос

`POST https://joinposter.com/api/settings.getCurrency`


### Параметры ответа settings.getCurrency

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит объект, внутри которого есть следующие параметры:

Параметр | Описание
-------- | --------
currency_id | Id валюты в Poster
currency_name | Название валюты
currency_code | Код валюты на терминале
currency_symbol | Unicode символ валюты, для рубля, драма и маната приходит HTML который на терминале отобразиться как иконка валюты
currency_code_iso | Цифровой код валюты по стандарту ISO 4217
