## menu.removeProduct: Удаление товара

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.removeProduct'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$product = [
    'product_id' => 48,
];

$data = sendRequest($url, 'post', $product);
```

> Пример ответа:

```json
{  
  "response":true
}
```

Метод удаляет товар

### HTTP запрос

`GET https://joinposter.com/api/menu.removeProduct`

### POST-параметры запроса menu.removeProduct

Параметр | Описание
-------- | --------
product_id | Id товара

### Параметры ответа menu.removeProduct

Параметр | Описание
-------- | --------
response | true, если товар успешно удалён
