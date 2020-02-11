## menu.getCategoryIngredients: Свойства категории ингредиентов

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.getCategoryIngredients'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&category_id=3'
 . '&1c=true';

$data = sendRequest($url);
```

> Пример ответа:

```json
{  
  "response":{  
    "category_id":"3",
    "name":"Алкоголь",
    "id_1c":"b80ffc81-0fc9-11e7-9ab4-ace01035e460"
  }
}
```

Метод возвращает свойства категории ингредиентов

### HTTP запрос

`GET https://joinposter.com/api/menu.getCategoryIngredients`

### GET-параметры запроса menu.getCategoryIngredients

Параметр | Описание
-------- | --------
category_id | Id категории ингредиентов
1c | Опциональный параметр, если значение `true` — возвращает в ответе id категории товаров в системе 1С. По умолчанию не передаётся.

### Параметры ответа menu.getCategoryIngredients

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит объект, внутри которого есть следующие параметры:

Параметр | Описание
-------- | --------
category_id | Id категории ингредиентов
category_name | Название категории ингредиентов
id_1c | Id категории ингредиентов в системе 1С
