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

Метод изменяет цену одного или нескольких товаров

### HTTP POST запрос

`POST https://joinposter.com/api/menu.updateProductPrice`

### POST-параметры запроса menu.updateProductPrice

Параметр | Описание
-------- | --------
spot_id | Id заведения, обязтаельный параметр для обновления цены с product_id
price | Стоимость товара в гривнах/рублях, обязательный параметр для обновления цены с product_id
product_id | Id товара, обязательный параметр, если нет массива products
modificator_id | Id модификатора, необязательный параметр
products | Массив товаров с ценами, необязательный параметр
modifications | Массив модификаторов товара или модификаций тех. карт

### POST-параметры массива products

Параметр | Описание
-------- | --------
id | Id товара
spot_id | Id заведения
price | Стоимость товара в гривнах/рублях

### POST-параметры массива modifications

Параметр | Описание
-------- | --------
id | Id модификатора товара или модификации тех.карты
spot_id | Id заведения, если это модификатор товара
price | Стоимость модификации в гривнах/рублях


### Параметры ответа menu.updateProductPrice без модификаций

Параметр | Описание
-------- | --------
success | 1 — в случае успешной операции

