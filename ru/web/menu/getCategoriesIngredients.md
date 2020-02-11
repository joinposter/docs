## menu.getCategoriesIngredients: Список категорий ингредиентов

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.getCategoriesIngredients'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&1c=true';

$data = sendRequest($url);
```

> Пример ответа:

```json
{  
  "response":[  
    {  
      "category_id":"3",
      "name":"Алкоголь",
      "id_1c":"b80ffc81-0fc9-11e7-9ab4-ace01035e460"
    },
    {  
      "category_id":"2",
      "name":"Мясо",
      "id_1c":null
    },
    {  
      "category_id":"1",
      "name":"Овощи",
      "id_1c":null
    },
    {  
      "category_id":"4",
      "name":"Фрукты",
      "id_1c":null
    }
  ]
}
```

Метод возвращает список категорий ингредиентов

### HTTP запрос

`GET https://joinposter.com/api/menu.getCategoriesIngredients`

### GET-параметры запроса menu.getCategoriesIngredients

Параметр | Описание
-------- | --------
1c | Опциональный параметр, если значение `true` — возвращает в ответе id категории товаров в системе 1С. По умолчанию не передаётся.

### Параметры ответа menu.getCategoriesIngredients

Параметр | Описание
-------- | --------
response | Массив объектов

Внутри параметра `response` лежит массив, в каждом элементе которого есть следующие параметры:

Параметр | Описание
-------- | --------
category_id | Id категории ингредиентов
category_name | Название категории ингредиентов
id_1c | Id категории ингредиентов в системе 1С
