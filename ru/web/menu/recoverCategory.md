## menu.recoverCategory: Восстановление категории

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.recoverCategory'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$category = [
    'category_id' => 48,
    'parent_category_id' => 10,
];

$data = sendRequest($url, 'post', $category);
```

> cURL example:

```php
curl -X POST \
  'http://poster.pos/api/menu.recoverCategory?token=687409:4164553abf6a031302898da7800b59fb' \
  -H 'cache-control: no-cache' \
  -H 'content-type: multipart/form-data \
  -F category_id=38 \
  -F parent_category_id=5 \

```

> Пример ответа:

```json
{  
  "response":true
}
```

Метод восстанавливает категорию

### HTTP запрос

`POST https://joinposter.com/api/menu.recoverCategory`

### POST-параметры запроса menu.recoverCategory

Параметр | Описание
-------- | --------
category_id | Id категории
parent_category_id | Id родительской категории меню

### Параметры ответа menu.recoverDish

Параметр | Описание
-------- | --------
response | true, если категория успешно восстановлена
