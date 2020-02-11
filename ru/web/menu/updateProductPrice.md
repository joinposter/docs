## menu.updateProductPrice: Изменение цены товара

> Пример запроса на изменение цены товара:

```php
<?php
$url = 'https://joinposter.com/api/menu.updateProductPrice'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$product = [
    'spot_id'          => 1,
    'price'            => '100',
    'product_id'       => 139,
    'modificator_id'   => 0,
];

$data = sendRequest($url, 'post', $product);
```

> Пример ответа:

```json
{  
  "success": 1
}
```

Метод изменяет цену товара

### HTTP POST запрос

`POST https://joinposter.com/api/menu.updateProductPrice`

### POST-параметры запроса menu.updateProductPrice

Параметр | Описание
-------- | --------
spot_id | Id заведения
price | Стоимость товара в гривнах\рублях
product_id | Id товара
modificator_id | Id модификатора


### Параметры ответа menu.updateProductPrice без модификаций

Параметр | Описание
-------- | --------
success | 1 — в случае успешной операции

