## menu.getCategories: Список категорий товаров

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.getCategories'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&fiscal=0';

$data = sendRequest($url);
```

> Пример ответа:

```json
{  
  "response":[  
    {  
      "category_id":"2",
      "category_name":"Роллы",
      "category_photo":"/upload/pos_cdb_888/menu/category_1420674791_2.jpg",
      "parent_category":"0",
      "category_color":"white",
      "category_hidden":"0",
      "sort_order":"999",
      "fiscal":"0",
      "nodiscount":"0",
      "tax_id":"0",
      "left":"3",
      "right":"4",
      "level":"1",
      "category_tag":"sushi"
    }
  ]
}
```

Метод возвращает список категорий товаров

### HTTP запрос

`GET https://joinposter.com/api/menu.getCategories`

### GET-параметры запроса menu.getCategories

Параметр | Описание
-------- | --------
fiscal | Фискальный признак категорий: 0 — не фискальные, 1 — фискальные. По умолчанию — все категории.
id_1c | Позволяет вернуть в ответе id категории товаров в системе 1С. В качестве значения необходимо передать true. По умолчанию не передаётся.

### Параметры ответа menu.getCategories

Параметр | Описание
-------- | --------
response | Массив объектов

Внутри параметра `response` лежит массив, в каждом элементе которого есть следующие параметры:

Параметр | Описание
-------- | --------
category_id | Id категории
category_name | Заголовок категории
category_photo | Фотография категории
parent_category | Id родительской категории
category_color | Цвет категории
category_hidden | Признак, что категория скрыта: 0 — не скрыта, 1 — скрыта
sort_order | Порядок сортировки
fiscal | Признак фискальности категории: 0 — не фискальная, 1 — фискальная
nodiscount | Признак, что распространяются скидки: 0 — не распространяются, 1 — распространяются
tax_id | Id налога
left | Id категории слева (по Nested Set)
right | Id катергории справа (по Nested Set)
level | Уровень вложенности ветки дерева категорий (по Nested Set)
category_tag | Предполагаемый тип продуктов в категории, который определил алгоритм машинного обучения. Например, `coffee`, `alcohol`, может быть `null`.
id_1c | Id категории товаров в системе 1С
