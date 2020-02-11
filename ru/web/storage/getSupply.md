## storage.getSupply: Свойства поставки

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/storage.getSupply'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&supply_id=46';

$data = sendRequest($url);
```

> Пример ответа:

```json
{  
   "response":{  
      "supply_id":"46",
      "in_inventory":"1",
      "storage_id":"1",
      "supplier_id":"1",
      "account_id":"",
      "date":"2017-05-18 09:07:00",
      "supply_sum":"6698828.90",
      "supply_comment":"",
      "supplier_name":"Закупщик",
      "ingredients":[  
         {  
            "ingredient_id":"66",
            "product_id":"86",
            "supply_ingredient_num":"3.0000000",
            "supply_ingredient_sum":"150.00",
            "ingredient_name":"Шен Да Бай Ча-Дзень Гу",
            "ingredient_unit":"kg",
            "pack_id":"3",
            "type":1,
            "ing_delete":"0",
            "tax_id":"0"
         }
      ]
   }
}
```

Метод возвращает свойства поставки  

### HTTP запрос

`GET https://joinposter.com/api/storage.getSupply`

### GET-параметры запроса storage.getSupply

Параметр | Описание
-------- | --------
supply_id | Обязательный параметр, указавающий id поставки

### Параметры ответа storage.getSupply

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит массив, в каждом элементе которого есть следующие параметры:

Параметр | Описание
-------- | --------
supply_id | id поставки
in_inventory | Инвенторизация по постевке: 0 — не было инвенторизации, 1 — была инвенторизация
storage_id | id склада на который поставляли
supplier_id | id поставщика
date | Дата поставки
account_id | id финансового счёта с которого списали поставку
supply_sum | Сумма поставки в копейках
supply_comment | Комментарий
storage_name | Название склада
supplier_name | Имя поставщика
ingredients | Список ингридиентов вошедших в поставку

Внутри параметра `ingredients` лежит массив, в каждом элементе которого есть следующие параметры:

Параметр | Описание
-------- | --------
ingredient_id | id ингридиента
product_id | id продукта
supply_ingredient_num | Количество ингредиента
supply_ingredient_sum | Общая сумма поставки по ингредиенту в копейках
ingredient_name | Название ингредиента
ingredient_unit | Единица измерения: kg — кг, p — шт, l — л
pack_id | id фасовки
type | Тип товара: принимает значение: 1 — полноценный ингредиент, 2 — товар, 3 — модификатор, 4 — производимая тех. карта, 5 — производимый полуфабрикат
ing_delete | Признак удален ли ингридиент: 0 — не удален, 1 — удален 
tax_id | id налога
