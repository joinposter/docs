## menu.getIngredient: Свойства ингредиента

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.getIngredient'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&ingredient_id=91'
 . '&1c=true';

$data = sendRequest($url);
```

> Пример ответа:

```json
{  
  "response":{  
    "ingredient_id":"91",
    "ingredient_name":"Jack Daniels",
    "category_id":"3",
    "ingredient_left":"442.85000",
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
    "partial_write_off":"0",
    "id_1c":"d70b49a7-0097-11e6-9c83-028037ec0200",
    "delete":"0",
    "hidden":"0"
  }
}
```

Метод возвращает свойства ингредиента

### HTTP запрос

`GET https://joinposter.com/api/menu.getIngredient`

### GET-параметры запроса menu.getIngredient

Параметр | Описание
-------- | --------
ingredient_id | Id ингредиента
1c | Опциональный параметр, если значение `true` — возвращает в ответе id категории товаров в системе 1С. По умолчанию не передаётся.

### Параметры ответа menu.getIngredient

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит объект, внутри которого есть следующие параметры:

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
