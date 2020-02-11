## menu.getPrepacks: Список полуфабрикатов

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.getPrepacks'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Пример ответа:

```json
{  
  "response":[  
    {  
      "product_id":"167",
      "ingredient_id":"0",
      "product_name":"Куринный бульон",
      "cost":"1222",
      "cost_netto":"1018",
      "out":171,
      "product_production_description":"",
      "ingredients":[  
        {  
          "structure_id":"45",
          "ingredient_id":"88",
          "pr_in_clear":"0",
          "pr_in_cook":"1",
          "pr_in_fry":"0",
          "pr_in_stew":"0",
          "pr_in_bake":"0",
          "structure_unit":"kg",
          "structure_type":"1",
          "structure_brutto":200,
          "structure_netto":170,
          "structure_lock":"1",
          "structure_selfprice":"1221",
          "structure_selfprice_netto":"1018",
          "ingredient_name":"Куриные крылья",
          "ingredient_unit":"kg",
          "ingredient_weight":"0",
          "ingredients_losses_clear":"0",
          "ingredients_losses_cook":"15",
          "ingredients_losses_fry":"16",
          "ingredients_losses_stew":"16",
          "ingredients_losses_bake":"16"
        },
        {  
          "structure_id":"46",
          "ingredient_id":"89",
          "pr_in_clear":"0",
          "pr_in_cook":"0",
          "pr_in_fry":"0",
          "pr_in_stew":"0",
          "pr_in_bake":"0",
          "structure_unit":"kg",
          "structure_type":"1",
          "structure_brutto":1,
          "structure_netto":1,
          "structure_lock":"1",
          "structure_selfprice":"1",
          "structure_selfprice_netto":"1",
          "ingredient_name":"Соль",
          "ingredient_unit":"kg",
          "ingredient_weight":"0",
          "ingredients_losses_clear":"0",
          "ingredients_losses_cook":"0",
          "ingredients_losses_fry":"0",
          "ingredients_losses_stew":"0",
          "ingredients_losses_bake":"0"
        }
      ]
    }
  ]
}
```

Метод возвращает список полуфабрикатов

### HTTP запрос

`GET https://joinposter.com/api/menu.getPrepacks`

### GET-параметры запроса menu.getPrepacks

Параметр | Описание
-------- | --------
token    | Авторизационный токен
format   | Опциональный параметр, указывающий формат выдачи ответа. Может быть xml или json. По умолчанию json.
1c       | Опциональный параметр, если значение `true` — возвращает в ответе id категории товаров в системе 1С. По умолчанию не передаётся.

### Параметры ответа menu.getPrepacks

Параметр | Описание
-------- | --------
response | Массив объектов

Внутри параметра `response` лежит массив, в каждом элементе которого есть следующие параметры:

Параметр | Описание
-------- | --------
product_id | Id полуфабриката в таблице товаров
ingredient_id | Id полуфабриката в таблице ингредиентов, если полуфабрикат производимый, иначе принимает 0
product_name | Название полуфабриката
cost | Себестоимость полуфабриката
cost_netto | Себестоимость полуфабриката без НДС. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
out | Вес полуфабриката
product_production_description | Описание процесса приготовления
id_1c | Id полуфабриката в системе 1С
ingredients | Ингредиенты входящие в состав полуфабриката

Внутри параметра `ingredients` лежит объект, внутри которого есть следующие параметры:

Параметр | Описание
-------- | --------
structure_id | Id элемента полуфабриката
ingredient_id | Id ингредиента
pr_in_clear | Признак, что используется метод приготовления «очистка»: 0 — не используется, 1 — используется
pr_in_cook | Признак, что используется метод приготовления «запекание»: 0 — не используется, 1 — используется
pr_in_fry | Признак, что используется метод приготовления «жарка»: 0 — не используется, 1 — используется
pr_in_stew | Признак, что используется метод приготовления «тущение»: 0 — не используется, 1 — используется
pr_in_bake | Признак, что используется метод приготовления «варка»: 0 — не используется, 1 — используется
structure_unit | Единица измерения элемента полуфабриката
structure_type | Тип элемента полуфабриката: 1 — ингредиент, 2 — полуфабрикат
structure_brutto | Брутто элемента полуфабриката
structure_netto | Нетто элемента полуфабриката
structure_lock | Зависимость нетто от брутто: 0 — ручная, 1 — автоматическая
structure_selfprice | Цена элемента полуфабриката
structure_selfprice_netto | Цена элемента полуфабриката без НДС. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
ingredient_name | Название ингредиента
ingredient_unit | Единица измерения ингредиента: kg — килограммы, p — штуки, l — литры
ingredient_weight | Количество списания ингредиента
ingredients_losses_clear | Коэффициент потерь при очистке ингредиента
ingredients_losses_cook | Коэффициент потерь при запекании ингредиента
ingredients_losses_fry | Коэффициент потерь при жарке ингредиента
ingredients_losses_stew | Коэффициент потерь при тущении ингредиента
ingredients_losses_bake | Коэффициент потерь при варке ингредиента
