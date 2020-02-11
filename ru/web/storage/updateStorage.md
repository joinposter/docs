## storage.updateStorage: Изменить склад

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/storage.updateStorage'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$storage = [
    "storage_id"      => 7,
    "storage_name"    => "Склад9 Кухня",
    "storage_adress"  => "Klenova 8"
];

$data = sendRequest($url, 'post', $storage);
```

> Пример ответа:

```json
{  
   "response":7
}
```

Метод изменяет склад

### HTTP запрос

`GET https://joinposter.com/api/storage.updateStorage`

### POST-параметры запроса storage.updateStorage

Параметр | Описание
-------- | --------
storage_id | Id склада 
storage_name | Название склада 
storage_adress | Адрес склада


### Параметры ответа storage.updateStorage

Параметр | Описание
-------- | --------
response | Id обновленного склада
