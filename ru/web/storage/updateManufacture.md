## storage.updateManufacture: Изменение данных производства

>  Пример запроса:

```php
<?
$url = 'https://joinposter.com/api/storage.updateManufacture?' .
  'format=json&token=687409:4164553abf6a031302898da7800b59fb';

$manufacture = [
    "manufacture_id"  => 7,
    "date"            => "2016-12-21 12:12:54",
    "storage_id"      => 1,
    "products" => [
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

$manufacture_id = sendRequest($url, 'post', $manufacture, true);
```

> Пример ответа:

```json
{
  "response":6
}
```
Запрос позволяет изменить данные существующего производства.

### HTTP запрос

`POST https://joinposter.com/api/storage.updateManufacture`

### POST-параметры запроса storage.updateManufacture

Параметр | Описание
-------- | --------
manufacture_id | id изменяемого производства
date | Дата производства
storage_id | id склада
products | Список тех.карт/полуфабрикатов, которые входят в производство

### Содержимое параметра products

Под словом сущность подразумевается тех.карта или полуфабрикат. Когда сущность производится в первый раз, то она получает уникальный ingredient_id, по которому можно будет получить её остатки на складах.

Параметр | Описание
-------- | --------
id | id сущности
num | Количество (в шт/кг)
type | Тип сущности: 1 — полуфабрикат, 2 — тех.карта

### Параметры ответа storage.updateManufacture

Параметр | Описание
-------- | --------
response | id измененного производства
