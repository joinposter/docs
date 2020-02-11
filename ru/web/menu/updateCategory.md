## menu.updateCategory: Изменение свойств категории товаров

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.updateCategory'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$category = [
    'category_id'     => 34,
    'category_name'   => 'Пицца',
    'parent_category' => 0,
    'category_color'  => 'red',
];

$data = sendRequest($url, 'post', $category);
```

> Пример ответа:

```json
{  
  "response": 34
}
```

Метод изменяет свойства категории товаров

### HTTP запрос

`GET https://joinposter.com/api/menu.updateCategory`

### POST-параметры запроса menu.updateCategory

Параметр | Описание
-------- | --------
category_id | Id категории товаров
category_name | Название категории товаров
parent_category | Id родительской категории
category_color | Цвет категории: white, red, orange, yellow, green, blue, navy-blue, purple, black, mint-blue, lime-green, pink. По умолчанию не передаётся.
category_hidden | Признак, что категория скрыта: 0 — не скрыта, 1 — скрыта. По умолчанию не передаётся.
tax_id | Id налога. По умолчанию не передаётся.

### Параметры ответа menu.updateCategory

Параметр | Описание
--------- | -----------
response | Id изменённой категории товаров
