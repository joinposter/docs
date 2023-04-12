## storage.getManufacture: Данные производства

>  Пример запроса:

```php
<?
$url = 'https://joinposter.com/api/storage.getManufacture' 
  . '?format=json'
  . '&token=687409:4164553abf6a031302898da7800b59fb'
  . '&manufacture_id=4';

$data = sendRequest($url);
```
> Пример ответа:

```json
{
  "response":{
    "manufacture_id":"4",
    "storage_name":"Склад 1",
    "storage_id":"1",
    "user_id":"4",
    "date":"2016-12-26 14:45:00",
    "sum":70.35,
    "sum_netto":58.63,
    "products":[
      {
        "ingredient_id":"205",
        "product_id":"134",
        "product_name":"Чай цветочный 360мл",
        "product_num":"3.0000",
        "type":"2"
      },
      {
        "ingredient_id":"204",
        "product_id":"137",
        "product_name":"Чай черный с чабрецом 360мл",
        "product_num":"2.0000",
        "type":"2"
      }
    ]
  }
}
```
Запрос возвращает данные конкретного производства.

### HTTP запрос

`GET https://joinposter.com/api/storage.getManufacture`

### GET-параметры запроса storage.getManufacture

Параметр | Описание
-------- | --------
manufacture_id | Id производства, для которого необходимо вернуть детальные данные

### Параметры ответа storage.getManufacture

Параметр | Описание
-------- | --------
manufacture_id | id производства
storage_name | Название склада
storage_id | id склада
user_id | id пользователя, который осуществил производство
date | Дата производства
sum | Общая сумма производства в гривнах
sum_netto | Общая сумма производства без НДС в гривнах\рублях. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
products | Список тех.карт/полуфабрикатов, которые входят в производство

### Содержимое параметра products

Под словом сущность подразумевается тех. карта или полуфабрикат. Когда сущность производится в первый раз, то она получает уникальный ingredient_id, по которому можно будет получить её остатки на складах.

Параметр | Описание
-------- | ---------
ingredient_id | уникальный ingredient_id сущности
product_id | id сущности
product_name | Название сущности
product_num | Количество в шт, кг или литрах
type | Тип сущности: 1 — полуфабрикат, 2 — тех.карта
