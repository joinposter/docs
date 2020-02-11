## storage.createSupplier: Создание поставщика

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/storage.createSupplier'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$supplier = [
    'supplier_name'    => 'Валера',
    'supplier_adress'  => 'пр. Петровского',
    'supplier_phone'   => 380671234567,
    'supplier_code'    => 32855961,
    'supplier_tin'     => 6449013711,
    'supplier_comment' => 'Мясо',
];

$data = sendRequest($url, 'post', $supplier);
```

> Пример ответа:

```json
{  
  "response":6
}
```

Метод создаёт поставщика

### HTTP POST запрос

`https://joinposter.com/api/storage.createSupplier`

### POST-параметры запроса storage.createSupplier

Параметр | Описание
-------- | --------
supplier_name | Имя поставщика
supplier_adress | Адрес
supplier_phone | Телефон
supplier_code | ЕГРПОУ
supplier_tin | ИНН
supplier_comment | Комментарий

### Параметры ответа storage.createSupplier

Параметр | Описание
-------- | --------
response | Id созданного поставщика
