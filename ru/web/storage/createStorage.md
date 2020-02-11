## storage.createStorage: Создать склад

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/storage.createStorage'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$storage = [
    "storage_name"    => "Склад3 Кухня",
    "storage_adress"  => "Klenova 3"
];

$data = sendRequest($url, 'post', $storage);
```

> Пример ответа:

```json
{  
   "response":6
}
```

Метод создает склад

### HTTP POST запрос

`GET https://joinposter.com/api/storage.createStorage`

### POST-параметры запроса storage.createStorage

Параметр | Описание
-------- | --------
storage_name | Название склада 
storage_adress | Адрес склада


### Параметры ответа storage.createStorage

Параметр | Описание
-------- | --------
response | Id созданного склада
