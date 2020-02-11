## storage.createWriteOff: Создание списания

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/storage.createWriteOff'
    . '?token=687409:4164553abf6a031302898da7800b59fb';

$writeOff = [
    "write_off" => [
        "storage_id"    => "1",
        "date"          => date("Y-m-d H:i:s"),
    ],
    "ingredient" => [
        [
            "id"        => "138",
            "type"      => "1",
            "weight"    => "3",
        ]
    ]
];

$data = sendRequest($url, 'post', $writeOff);
```

> Пример ответа:

```json
{
  "success":1,
  "response":6
}
```

Метод создает списание


### HTTP запрос

`POST https://joinposter.com/api/storage.createWriteOff`

### POST-параметры запроса storage.createWriteOff

Параметр | Описание
-------- | --------
date | Дата поставки в формате `Y-m-d H:i:s` 
storage_id | id склада с которого делаем списание 
ingredient | Массив объектов для списания
reason_id | Опциональный параметр, id причины списания

Каждый объект массива `ingredient` содержит следующие параметры  

Параметр | Описание
-------- | --------
id | id ингредиента, товара или модификатора товара 
type | Тип списываемого объекта: товар — 1, тех.карта — 2, полуфабрикат — 3, ингредиент — 4, модификатор товара — 5
weight | Количество списываемого ингредиента
packing | Опциональный параметр, id фасовки 
reason | Опциональный параметр, комментарий к списаному товару

### Параметры ответа storage.createWriteOff

Параметр | Описание
-------- | --------
success | Статус выполнения операции: 1 — успешно, 0 — нет
response | id созданного списания
