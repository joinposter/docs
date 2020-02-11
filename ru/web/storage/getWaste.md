## storage.getWaste: Данные ручного списания

>  Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/storage.getWaste'
  . '?token=687409:4164553abf6a031302898da7800b59fb'
  . '&waste_id=1';

$data = sendRequest($url);
```

> Пример ответа:

```json
{
  "response": {
    "waste_id": 1,
    "total_sum": 2800,
    "total_sum_netto": 2333,
    "user_id": 1,
    "storage_id": 1,
    "date": "2017-04-26 14:30:02",
    "reason_id": 1,
    "reason_name": "Истек срок годности",
    "elements": [
      {
        "type": 8,
        "product_id": 8,
        "modificator_id": 2,
        "count": 1,
        "ingredients": [
          {
            "write_off_id": 118,
            "ingredient_id": 21,
            "product_id": 8,
            "modificator_id": 2,
            "prepack_id": 0,
            "weight": 1,
            "unit": "p",
            "cost": 800,
            "cost_netto": 667
          }
        ]
      },
      {
        "type": 3,
        "product_id": 4,
        "count": 1,
        "ingredients": [
          {
            "write_off_id": 121,
            "ingredient_id": 16,
            "product_id": 4,
            "modificator_id": 0,
            "prepack_id": 0,
            "weight": 1,
            "unit": "kg",
            "cost": 500,
            "cost_netto": 417
          },
          {
            "write_off_id": 122,
            "ingredient_id": 15,
            "product_id": 4,
            "modificator_id": 0,
            "prepack_id": 0,
            "weight": 1,
            "unit": "kg",
            "cost": 1500,
            "cost_netto": 1250
          }
        ]
      }
    ]
  }
}
```

Метод возвращает детальные данные конкретного ручного списания

### HTTP запрос

`GET https://joinposter.com/api/storage.getWaste`

### GET-параметры запроса storage.getWaste

Параметр | Описание
--------- | -----------
waste_id | id ручного списания для которого необходимо вернуть детальные данные

### Параметры ответа storage.getWaste

Параметр | Описание
--------- | -----------
waste_id | id ручного списания
total_sum | Общая сумма списания
total_sum_netto | Общая сумма списания без НДС. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
user_id | id пользователя, который произвёл списание
storage_id | id склада с которого было произведено списание
date | Дата списания
reason_id | id причины списания
reason_name | Причина списания
elements | Список списанных сущностей.

У каждого элемента внутри `elements` следующие параметры:

Параметр | Описание
--------- | -----------
type | Тип списанной сущности: 1 — товар, 2 — тех. карта, 3 — полуфабрикат, 8 — модификатор, 10 — ингредиент
product_id | id товара
modificator_id | id модификатора
count | Количество списанных конкретных сущностей
ingredients | Массив из ингредиентов списания 

У каждого элемента внутри `ingredients` следующие параметры:

Параметр | Описание
--------- | -----------
ingredient_id | id ингредиента
write_off_id | id конкретного списания
prepack_id | id фасовки
product_id | id товара
weight | Количество списания в килограммах, литрах или единицах
unit | unit | Единица измерения: kg — кг, p — шт, l — л
cost | Общая сумма списания по этому ингредиенту в копейках. Если вам нужно узнать себестоимость, разделите `cost` на `weight`.
cost_netto | Общая сумма списания по этому ингредиенту без НДС в копейках. Если вам нужно узнать себестоимость, разделите `cost` на `weight`. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
