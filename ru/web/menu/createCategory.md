# menu.createCategory: Создание категории товаров

<details>
<summary>Пример запроса (Click to expand)</summary>


```php
<?php
$url = 'https://joinposter.com/api/menu.createCategory'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$category = [
    'category_name'   => 'Пицца',
    'parent_category' => 0,
    'category_color'  => 'yellow',
    'category_hidden' => 0,
    'tax_id'          => 0,
];

$data = sendRequest($url, 'post', $category);
```

</details>



<details>
<summary>Пример ответа (Click to expand)</summary>


```json
{  
  "response":52
}
```

</details>

Метод создаёт категорию товаров

## HTTP запрос

`GET https://joinposter.com/api/menu.createCategory`

## POST-параметры запроса menu.createCategory

Параметр | Описание
-------- | --------
category_name | Название категории товаров
parent_category | Id родительской категории
category_color | Цвет категории: white, red, orange, yellow, green, blue, navy-blue, purple, black, mint-blue, lime-green, pink. По умолчанию принимает white. 
category_hidden | Признак, что категория скрыта: 0 — не скрыта, 1 — скрыта. По умолчанию принимает 0.
tax_id | Id налога. По умолчанию принимает 0.

## Параметры ответа menu.createCategory

Параметр | Описание
-------- | --------
response | Id созданной категории товаров
