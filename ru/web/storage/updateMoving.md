## storage.updateMoving: Изменение перемещения

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/storage.updateMoving'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$moving = [
    "moving" => [
        "moving_id"     => "16",
        "date"          => "2015-11-18 22:35:54",
        "from_storage"  => "1",
        "to_storage"    => "2"
    ],
    "ingredient" => [
        [
            "id"        => "138",
            "type"      => "1",
            "num"       => "3",
        ]
    ]
];

$data = sendRequest($url, 'post', $moving);
```

> Пример ответа:

```json
{
  "success":1,
  "response":16
}
```

Метод изменяет перемещение

### HTTP запрос

`POST https://joinposter.com/api/storage.updateMoving`

### POST-параметры запроса storage.updateMoving

Параметр | Описание
-------- | --------
moving_id | id перемещения которое редактируем
date | Дата и время списания в формате `Ymd` 
from_storage_id | id склада c которого делаем перемещение 
to_storage_id | id склада  на который делаем перемещение 
ingredient | Массив объектов для перемещения

Каждый объект массива `ingredient` содержит следующие параметры  

Параметр | Описание
-------- | --------
id | id ингредиента, товара или модификатора товара 
type | Тип списываемого объекта: товар — 1, ингредиент — 4, модификатор товара — 5
num | Количество списываемого ингредиента 
reason | Опциональный параметр, причина списания
packing | Опциональный параметр, id фасовки

### Параметры ответа storage.updateMoving

Параметр | Описание
-------- | --------
success | Статус выполнения операции: 1 — успешно, 0 — нет
response | id обновленного перемещения
