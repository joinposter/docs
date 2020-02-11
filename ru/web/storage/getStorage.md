## storage.getStorage: Свойства склада

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/storage.getStorage'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&storage_id=1';

$data = sendRequest($url);
```

> Пример ответа:

```json
{  
   "response":{
      "storage_id":"1",
      "storage_name":"Склад Кухня",
      "storage_adress":"",
      "delete":"0"
   }
}
```

Метод возвращает свойства склада

### HTTP GET запрос

`GET https://joinposter.com/api/storage.getStorage`

### GET-параметры запроса storage.getStorage

Параметр | Описание
-------- | --------
storage_id | Обязательный параметр, обозначает id склада

### Параметры ответа storage.getStorage

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит объект, в котором есть следующие параметры:

Параметр | Описание
-------- | --------
storage_id | Id склада
storage_name | Название склада
storage_adress | Адрес склада
delete | Признак удален ли склад: 1 — удален, 0 — нет
