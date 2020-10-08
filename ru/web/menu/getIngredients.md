## menu.getIngredients: Список ингредиентов

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.getIngredients'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Пример ответа:

```json
{  
  "response":[  
    {  
      "ingredient_id":"91",
      "ingredient_name":"Jack Daniels",
      "ingredient_barcode": "",
      "category_id":"3",
      "ingredient_left":"443.45000",
      "limit_value":"0",
      "time_notif":"0",
      "ingredient_unit":"l",
      "ingredient_weight":0,
      "ingredients_losses_clear":"0",
      "ingredients_losses_cook":"0",
      "ingredients_losses_fry":"0",
      "ingredients_losses_stew":"0",
      "ingredients_losses_bake":"0",
      "ingredients_type":"1",
      "partial_write_off":"0"
    },
    {  
      "ingredient_id":"73",
      "ingredient_name":"Авокадо",
      "ingredient_barcode": "",
      "category_id":"0",
      "ingredient_left":"22.00000",
      "limit_value":"0",
      "time_notif":"0",
      "ingredient_unit":"kg",
      "ingredient_weight":0,
      "ingredients_losses_clear":"11",
      "ingredients_losses_cook":"0",
      "ingredients_losses_fry":"0",
      "ingredients_losses_stew":"0",
      "ingredients_losses_bake":"0",
      "ingredients_type":"1",
      "partial_write_off":"0"
    },
    {  
      "ingredient_id":"74",
      "ingredient_name":"Айсберг с-т",
      "ingredient_barcode": "",
      "category_id":"0",
      "ingredient_left":"379.09000",
      "limit_value":"0",
      "time_notif":"0",
      "ingredient_unit":"kg",
      "ingredient_weight":0,
      "ingredients_losses_clear":"10",
      "ingredients_losses_cook":"0",
      "ingredients_losses_fry":"0",
      "ingredients_losses_stew":"0",
      "ingredients_losses_bake":"0",
      "ingredients_type":"1",
      "partial_write_off":"0"
    }
  ]
}
```

Метод возвращает список ингредиентов

### HTTP запрос

`GET https://joinposter.com/api/menu.getIngredients`

### GET-параметры запроса menu.getIngredients

Параметр | Описание
-------- | --------
id_1c | Опциональный параметр, если значение `true` — возвращает в ответе id категории товаров в системе 1С. По умолчанию не передаётся.

### Параметры ответа menu.getIngredients

Параметр | Описание
-------- | --------
response | Массив объектов

Внутри параметра `response` лежит массив, в каждом элементе которого есть следующие параметры:

Параметр | Описание
-------- | --------
ingredient_id | Id ингредиента
ingredient_name | Название ингредиента
category_id | Id категории в которой находится ингредиент
ingredient_left | Остаток по ингредиенту
limit_value | Лимит по ингредиенту на складе
time_notif | Время последнего уведомления о достижения лимита по ингредиенту на складе
ingredient_unit | Единица измерения ингредиента: kg — килограммы, p — штуки, l — литры
ingredient_weight | Вес ингредиента, если ингредиент штучный
ingredients_losses_clear | Коэффициент потерь при очистке ингредиента, если ингредиент не штучный
ingredients_losses_cook | Коэффициент потерь при запекании ингредиента, если ингредиент не штучный
ingredients_losses_fry | Коэффициент потерь при жарке ингредиента, если ингредиент не штучный
ingredients_losses_stew | Коэффициент потерь при тущении ингредиента, если ингредиент не штучный
ingredients_losses_bake | Коэффициент потерь при варке ингредиента, если ингредиент не штучный
ingredients_type | Тип ингредиента: 1 — ингредиент, 2 - системный ингредиент
partial_write_off | Признак, что можно списывать штучный ингредиент, как дробный: 0 — нельзя, 1 — можно
id_1c | Id ингредиента в системе 1С
delete | Признак, что ингредиент удалён: 0 — не удалён, 1 — удалён
hidden | Признак, что ингредиент скрыт: 0 — не скрыт, 1 — скрыт
