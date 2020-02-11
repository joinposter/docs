## menu.getProduct: Свойства товара или тех. карты

> Пример запроса получения свойств товара:

```php
<?php
$url = 'https://joinposter.com/api/menu.getProduct'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&product_id=142';

$data = sendRequest($url);
```

> Пример ответа:

```json
{  
  "response":{  
    "barcode":"",
    "category_name":"Свежевыжатые соки",
    "unit":"",
    "cost":"1880",
    "cost_netto":"1567",
    "fiscal":"0",
    "hidden":"0",
    "menu_category_id":"16",
    "workshop":"4",
    "nodiscount":"0",
    "photo":"/upload/4/menu/product_1403094607_140.jpg",
    "product_code":"",
    "product_id":"140",
    "product_name":"Апельсиновый",
    "sort_order":"1",
    "tax_id":"0",
    "product_tax_id":"0",
    "type":"3",
    "weight_flag":"0",
    "color":"white",
    "spots":[  
      {  
        "spot_id":"1",
        "price":"40000",
        "profit":"38120",
        "profit_netto":"31767",
        "visible":"1"
      },
      {  
        "spot_id":"2",
        "price":"40000",
        "profit":"38120",
        "profit_netto":"31767",
        "visible":"1"
      }
    ],
    "ingredient_id":"10",
    "cooking_time": "1201",
    "out":"0"
  }
}
```

> Пример запроса получения свойств тех. карты:

```php
<?php
$url = 'https://joinposter.com/api/menu.getProduct'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&product_id=175';

$data = sendRequest($url);
```

> Пример ответа:

```json
{  
  "response":{  
    "barcode":"123456",
    "category_name":"Коктейли",
    "unit":"kg",
    "cost":"444",
    "cost_netto":"370",
    "fiscal":"0",
    "menu_category_id":"39",
    "workshop":"1",
    "nodiscount":"0",
    "photo":"/upload/pos_cdb_4/menu/product_1439375876_175.jpg",
    "product_code":"",
    "product_id":"175",
    "product_name":"Manhattan Jack",
    "sort_order":"999",
    "tax_id":"0",
    "product_tax_id":"0",
    "type":"2",
    "weight_flag":"0",
    "color":"white",
    "spots":[  
      {  
        "spot_id":"1",
        "price":"60000",
        "profit":"59556",
        "profit_netto":"49630",
        "visible":"1"
      },
      {  
        "spot_id":"2",
        "price":"60000",
        "profit":"59556",
        "profit_netto":"49630",
        "visible":"1"
      }
    ],
    "ingredient_id":"0",
    "out":97,
    "product_production_description":"",
    "ingredients":[  
      {  
        "structure_id":"52",
        "ingredient_id":"92",
        "pr_in_clear":"0",
        "pr_in_cook":"0",
        "pr_in_fry":"0",
        "pr_in_stew":"0",
        "pr_in_bake":"0",
        "structure_unit":"l",
        "structure_type":"1",
        "structure_brutto":30,
        "structure_netto":30,
        "structure_lock":"1",
        "structure_selfprice":"102",
        "structure_selfprice_netto":"85",
        "ingredient_name":"Красный вермут",
        "ingredient_unit":"l",
        "ingredient_weight":"0",
        "ingredients_losses_clear":"0",
        "ingredients_losses_cook":"0",
        "ingredients_losses_fry":"0",
        "ingredients_losses_stew":"0",
        "ingredients_losses_bake":"0"
      },
      {  
        "structure_id":"53",
        "ingredient_id":"91",
        "pr_in_clear":"0",
        "pr_in_cook":"0",
        "pr_in_fry":"0",
        "pr_in_stew":"0",
        "pr_in_bake":"0",
        "structure_unit":"l",
        "structure_type":"1",
        "structure_brutto":60,
        "structure_netto":60,
        "structure_lock":"1",
        "structure_selfprice":"313",
        "structure_selfprice_netto":"261",
        "ingredient_name":"Jack Daniels",
        "ingredient_unit":"l",
        "ingredient_weight":"0",
        "ingredients_losses_clear":"0",
        "ingredients_losses_cook":"0",
        "ingredients_losses_fry":"0",
        "ingredients_losses_stew":"0",
        "ingredients_losses_bake":"0"
      }
    ]
  }
}
```

Метод возвращает свойства товара или тех. карты

### HTTP запрос

`GET https://joinposter.com/api/menu.getProduct`

### GET-параметры запроса menu.getProduct

Параметр | Описание
-------- | --------
product_id | Id товара или тех. карты

### Параметры ответа menu.getProduct

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит объект, внутри которого есть следующие параметры:

Параметр | Описание
-------- | --------
barcode | Штриховой код товара
category_name | Название категории в которой содержится товар
unit | Единица измерения товара
cost | Себестоимость товара в копейках
cost_netto | Себестоимость товара без НДС в копейках. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
fiscal | Фискальный признак товара: 0 — не фискальный, 1 — фискальный
menu_category_id | Id категории в которой содержится товар
workshop | Id цеха товара
nodiscount | Признак, могут ли применяться скидки к этому товару: 0 — не могут, 1 — могут
photo | Фотография товара
product_code | Складская учётная единица товара
product_id | Id товара
product_name | Название товара
sort_order | Порядок сортировки товара
tax_id | Id налога товара
product_tax_id | Признак, что налог товара унаследован от налога категории: 0 — не унаследован, 1 — унаследован
type | Тип товара: 1 — полуфабрикат, 2 — тех.карта, 3 — товар
weight_flag | Признак, что товар весовой: 0 — не весовой, 1 — весовой
color | Цвет карточки товара в терминале
spots | Заведения в которых доступен товар
ingredient_id | Id ингредиента (возвращается, если товар)
cooking_time | Время приготовления блюда в секундах
product_production_description | Описание процесса приготовления
out | Сумма нетто всех ингредиентов тех. карты, для товара всегда 0
ingredients | Список ингредиентов (возвращается, если тех. карта)

Внутри параметра `spots` лежит массив, в каждом элементе которого есть следующие параметры:

Параметр | Описание
-------- | --------
spot_id | Id заведения
price | Цена на товар в этом заведении в копейках
profit | Чистая прибыль с товара в этом заведении в копейках
profit_netto | Чистая прибыль с товара в этом заведении без НДС в копейках. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
visible | Признак, что товар виден в этом заведении: 0 — скрыт, 1 — виден

Внутри параметра `ingredients` лежит массив, в каждом элементе которого есть следующие параметры:

Параметр | Описание
-------- | --------
structure_id | Id элемента тех. карты
ingredient_id | Id ингредиента
pr_in_clear | Признак, что используется метод приготовления «очистка»: 0 — не используется, 1 — используется
pr_in_cook | Признак, что используется метод приготовления «запекание»: 0 — не используется, 1 — используется
pr_in_fry | Признак, что используется метод приготовления «жарка»: 0 — не используется, 1 — используется
pr_in_stew | Признак, что используется метод приготовления «тущение»: 0 — не используется, 1 — используется
pr_in_bake | Признак, что используется метод приготовления «варка»: 0 — не используется, 1 — используется
structure_unit | Единица измерения элемента тех. карты
structure_type | Тип элемента тех. карты: 1 — ингредиент, 2 — полуфабрикат
structure_brutto | Брутто элемента тех. карты
structure_netto | Нетто элемента тех. карты
structure_lock | Зависимость нетто от брутто: 0 — ручная, 1 — автоматическая
structure_selfprice | Цена элемента тех. карты
structure_selfprice_netto | Цена элемента тех. карты без НДС. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
ingredient_name | Название ингредиента
ingredient_unit | Единица измерения ингредиента
ingredient_weight | Количество списания ингредиента
ingredients_losses_clear | Коэффициент потерь при очистке ингредиента
ingredients_losses_cook | Коэффициент потерь при запекании ингредиента
ingredients_losses_fry | Коэффициент потерь при жарке ингредиента
ingredients_losses_stew | Коэффициент потерь при тущении ингредиента
ingredients_losses_bake | Коэффициент потерь при варке ингредиента
