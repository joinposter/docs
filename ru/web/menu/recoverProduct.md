## menu.recoverProduct: Восстановление товара

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.recoverProduct'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$product = [
    'product_id' => 48,
    'menu_category_id' => 10,
    'workshop' => 3,
    'tax_id' => 1,
];

$data = sendRequest($url, 'post', $product);
```

> cURL example:

```php
curl -X POST \
  'http://poster.pos/api/menu.recoverProduct?token=687409:4164553abf6a031302898da7800b59fb' \
  -H 'cache-control: no-cache' \
  -H 'content-type: multipart/form-data \
  -F product_id=38 \
  -F menu_category_id=5 \
  -F workshop=4 \
  -F tax_id=2

```

> Пример ответа:

```json
{  
  "response":true
}
```

Метод восстанавливает товар

### HTTP запрос

`POST https://joinposter.com/api/menu.removeProduct`

### POST-параметры запроса menu.recoverProduct

Параметр | Описание
-------- | --------
product_id | Id товара
menu_category | Id категории меню
workshop | Id цеха
tax_id | Id налога

### Параметры ответа menu.recoverProduct

Параметр | Описание
-------- | --------
response | true, если товар успешно восстановлен
