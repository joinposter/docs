## storage.updateSupply: Изменение поставки

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/storage.updateSupply'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$supply = [
    "supply" => [
        "supply_id"     => "51",
        "supplier_id"   => "1",
        "storage_id"    => "1",
        "date"          => date("Y-m-d H:i:s"),
    ],
    "ingredient" => [
        [
            "id"        => "138",
            "type"      => "1",
            "num"       => "3",
            "sum"       => "6",
        ]
    ]
];

$data = sendRequest($url, 'post', $supply);
```

> Пример ответа:

```json
{
  "success":1,
  "response":"51"
}
```

Метод изменяет поставку

### HTTP запрос

`POST https://joinposter.com/api/storage.updateSupply`

### POST-параметры запроса storage.updateSupply
Параметр | Описание
-------- | --------
supply_id | id поставки которую редактируем
date | Дата поставки в формате `Y-m-d H:i:s` 
supplier_id | id поставщика 
storage_id | Обязательный параметр, id склада на который делаем поставку
supply_comment | Комментарий к поставке
account_id | Опциональный параметр, id счета в бухгалтерии к которому привязываем поставку 
ingredient | Массив объектов для поставки

Каждый объект массива `ingredient` содержит следующие параметры  

Параметр | Описание
-------- | --------
id | id ингредиента, товара или модификатора товара 
type | Тип списываемого объекта: товар — 1, ингредиент — 4, модификатор товара — 5
num | Количество списываемого ингредиента 
sum | Цена за единицу в гривнах\рублях 
packing | Опциональный параметр, id фасовки 

### Параметры ответа storage.updateSupply

Параметр | Описание
-------- | --------
success | Статус выполнения операции: 1 — успешно, 0 — нет
response | id обновленной поставки
