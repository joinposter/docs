## transactions.getTransactionsWriteOffs: Списания по чекам

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/transactions.getTransactionsWriteOffs'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&date_from=2017-11-30'
 . '&date_to=2017-11-30'
 . '&per_page=10'
 . '&page=5';

$data = sendRequest($url);
```

> Пример ответа:

```json
{  
  "response":{  
    "count":41,
    "page":{  
      "per_page":10,
      "page":5,
      "count":1
    },
    "data":[  
      {  
        "transaction_id":25221,
        "write_offs":[  
          {  
            "write_off_id":143731,
            "storage_id":3,
            "product_id":469,
            "modificator_id":0,
            "ingredient_id":30,
            "prepack_id":0,
            "cost":26.68,
            "cost_netto":22.23,
            "weight":0.16,
            "unit":"kg",
            "reason":""
          }
        ]
      }
    ]
  }
}
```

Метод возвращает списания по чекам в диапазоне дат и с постраничной разбивкой

### HTTP GET запрос

`https://joinposter.com/api/transactions.getTransactionsWriteOffs`

### GET-параметры запроса transactions.getTransactionsWriteOffs

Параметр | Описание
-------- | --------
date_from | Дата начала выборки, формат "Y-m-d"
date_to | Дата конца выборки, формат "Y-m-d"
per_page | Количество чеков на одной странице. По умолчанию принимает 100, максимальное значение — 1000.
page | Номер страницы, по умолчанию принимает 1

### Параметры ответа transactions.getTransactionsWriteOffs

Внутри параметра `response` лежит объект, внутри которого есть следующие параметры:

Параметр | Описание
-------- | --------
count | Общее количество чеков в выбранном диапазоне дат
page | Информация о странице
data | Информация по чекам

Внутри параметра `page` лежит объект, внутри которого есть следующие параметры:

Параметр | Описание
-------- | --------
per_page | Количество чеков на одной странице
page | Номер текущей страницы
count | Количество чеков на текущей странице 

Внутри параметра `data` лежит массив, в каждом элементе которого есть следующие параметры:

Параметр | Описание
-------- | --------
transaction_id | Id чека
write_offs | Списания по чеку

Внутри параметра `write_offs` лежит массив, в каждом элементе которого есть следующие параметры:

Параметр | Описание
-------- | --------
write_off_id | Id списания
storage_id | Id склада с которого произошло списание
product_id | Id товара
modificator_id | Id модификатора
ingredient_id | Id ингредиента. Для произведённых тех. карт и полуфабрикатов будет возвращён [системный id ингредиента сущности](/docs/v3/web/storage/getManufacture)
prepack_id | Id полуфабриката
cost | Стоимость
cost_netto | Стоимость без НДС
weight | Количество
unit | Единица измерения: kg — килограммы, p — штуки, l — литры
reason | Причина списания

<aside class="info">
Обратите внимание:
`prepack_id` возвращает значение только в том случае, если полуфабрикат был произведён.
Иначе будут возвращены `ingredient_id` / `prepack_id` из которых состоит этот полуфабрикат.
</aside>
