## menu.removeCategory: Удаление категории товаров

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.removeCategory'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$category = [
    'category_id' => 52,
];

$data = sendRequest($url, 'post', $category);
```

> Пример ответа:

```json
{  
  "response":true
}
```

Метод удаляет категорию товаров

### HTTP запрос

`GET https://joinposter.com/api/menu.removeCategory`

### POST-параметры запроса menu.removeCategory

Параметр | Описание
-------- | --------
category_id | Id категории товаров

### Параметры ответа menu.removeCategory

Параметр | Описание
-------- | --------
response | true, если категория товаров успешно удалена
