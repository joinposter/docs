## storage.getStorages: Получить все склады

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/storage.getStorages'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Пример ответа:

```json
{
  "response":[
    {
      "storage_id":"1",
      "storage_name":"Склад Кухня",
      "storage_adress":"",
      "delete":"0"
    },
    {
      "storage_id":"2",
      "storage_name":"Склад Бар",
      "storage_adress":"",
      "delete":"0"
    }
  ]
}
```

Метод возвращает все склады

### HTTP запрос

`GET https://joinposter.com/api/storage.getStorages`

### Параметры ответа storage.getStorages

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит массив, в каждом элементе которого есть следующие параметры:

Параметр | Описание
-------- | --------
storage_id | id склада
storage_name | Название склада
storage_adress | Адрес склада
delete | Признак удален ли склад: 1 — удален, 0 — нет
