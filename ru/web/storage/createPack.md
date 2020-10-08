## storage.createPack: Создание фасовки

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/storage.createPack'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$pack = [
    'name' => 'Ящик',
    'unit' => 'kg',
    'count' => 0.5,
];

$data = sendRequest($url, 'post', $pack);
```

> Пример запроса:

```cURL
curl --location --request POST 'https://joinposter.com/api/storage.createPack?token=687409:4164553abf6a031302898da7800b59fb' \
--header 'Content-Type: application/json' \
--data-raw '{
  "name": "Ящик",
  "unit": "kg",
  "count": 0.5
}'
```

> Пример ответа:

```json
{  
  "response": 5
}
```

Метод создаёт фасовку

### HTTP POST запрос

`POST https://joinposter.com/api/storage.createPack`

### POST-параметры запроса storage.createPack

Параметр | Описание
-------- | --------
name | Название фасовки 
unit | Единица измерения: kg — кг, p — шт, l — л
count | Количество в шт, кг или литрах

### Параметры ответа storage.createPack

Параметр | Описание
-------- | --------
response | Id созданной фасовки
