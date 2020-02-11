## storage.createManufacture: Создание производства

>  Пример запроса:

```php
<?
$url = 'https://joinposter.com/api/storage.createManufacture' 
  . '?format=json'
  . '&token=687409:4164553abf6a031302898da7800b59fb';

$manufacture = [
    "date"          => "2016-12-21 11:12:54",
    "storage_id"    => 1,
    "products"      => [
        [
            "id"    => 64,
            "type"  => 1,
            "num"   => 3
        ],
        [
            "id"    => 65,
            "type"  => 1,
            "num"   => 25
        ],
    ]
];

$data = sendRequest($url, 'post', $manufacture, true);
```

> Пример ответа:

```json
{
  "response":6
}
```

Запрос создает производство тех.карт и полуфабрикатов

### HTTP запрос

`POST https://joinposter.com/api/storage.createManufacture`

### POST-параметры запроса storage.createManufacture

Параметр | Описание
-------- | --------
date | Дата производства
storage_id | id склада
products | Список тех.карт или полуфабрикатов, которые входят в производство

### Содержимое параметра products

Под словом сущность подразумевается тех.карта или полуфабрикат. Когда сущность производится в первый раз, то она получает уникальный ingredient_id, по которому можно будет получить её остатки на складах.

Параметр | Описание
-------- | --------
id | id сущности
num | Количество в шт или кг
type | Тип сущности: 1 — полуфабрикат, 2 — тех.карта

### Параметры ответа storage.createManufacture

Параметр | Описание
-------- | --------
response | id созданного производства
