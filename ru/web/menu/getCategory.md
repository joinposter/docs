## menu.getCategory: Свойства категории товаров

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.getCategory'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&category_id=30'
 . '&1c=true';

$data = sendRequest($url);
```

> Пример ответа:

```json
{  
  "response":{  
    "category_id":30,
    "category_name":"Бар",
    "category_photo":null,
    "category_photo_origin":null,
    "parent_category":0,
    "category_color":"yellow",
    "category_hidden":0,
    "sort_order":3,
    "fiscal":0,
    "nodiscount":0,
    "tax_id":2,
    "left":7,
    "right":42,
    "level":1,
    "category_tag":"alco",
    "visible":[
      {
        "spot_id": 1,
        "visible": 1
      },
      {
        "spot_id": 2,
        "visible": 0
      }
    ],
    "id_1c":"9c68dbc9-b255-11e6-9a8f-ace01035e460"
  }
}
```

Метод возвращает свойства категории товаров

### HTTP запрос

`GET https://joinposter.com/api/menu.getCategory`

### GET-параметры запроса menu.getCategory

Параметр | Описание
-------- | --------
category_id | Id категории
1c | Позволяет вернуть в ответе id категории товаров в системе 1С. В качестве значения необходимо передать true. По умолчанию не передаётся.

### Параметры ответа menu.getCategory

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит объект, внутри которого есть следующие параметры:

Параметр | Описание
-------- | --------
category_id           | Id категории
category_name         | Название категории
category_photo        | Фотография категории
category_photo_origin | Оригинал загруженной фотографии
parent_category       | Id родительской категории
category_color        | Цвет категории
category_hidden       | Признак, что категория скрыта: 0 — не скрыта, 1 — скрыта
sort_order            | Порядок сортировки
fiscal                | Признак фискальности категории: 0 — не фискальная, 1 — фискальная
nodiscount            | Признак, что распространяются скидки: 0 — не распространяются, 1 — распространяются
tax_id                | Id налога
left                  | Id категории слева (по Nested Set)
right                 | Id категории справа (по Nested Set)
level                 | Уровень вложенности ветки дерева категорий (по Nested Set)
category_tag          | Предполагаемый тип продуктов в категории, который определил алгоритм машинного обучения. Например, `coffee`, `alcohol`, может быть `null`.
visible               | Массив в каждом объекте которого есть признак видимости категории в заведении
id_1c                 | Id категории товаров в системе 1С

Внутри параметра `visible` лежит массив, в каждом элементе которого есть следующие параметры:

Параметр | Описание
-------- | --------
spot_id | Id заведения
visible | Признак, что категория видна в этом заведении: 0 — скрыта, 1 — видна
