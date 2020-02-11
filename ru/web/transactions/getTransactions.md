## transactions.getTransactions: Список чеков

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/transactions.getTransactions'
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
        "table_id":1,
        "spot_id":1,
        "client_id":68,
        "sum":360,
        "payed_sum":0,
        "payed_cash":0,
        "payed_card":0,
        "payed_cert":0,
        "payed_bonus":0,
        "payed_third_party":0,
        "round_sum":0,
        "pay_type":3,
        "reason":0,
        "tip_sum": 0,
        "bonus":0,
        "discount":100,
        "print_fiscal":0,
        "date_close":"2017-11-30 13:48:09",
        "products":[  
          {  
            "product_id":469,
            "modification_id":0,
            "type":2,
            "workshop_id":2,
            "num":2,
            "product_sum":360,
            "payed_sum":0,
            "cert_sum":0,
            "bonus_sum":0,
            "bonus_accrual":0,
            "round_sum":0,
            "discount":100,
            "tax_fiscal":1
          }
        ]
      }
    ]
  }
}
```

Метод возвращает список чеков с товарами в диапазоне дат и с постраничной разбивкой

### HTTP GET запрос

`https://joinposter.com/api/transactions.getTransactions`

### GET-параметры запроса transactions.getTransactions

Параметр | Описание
-------- | --------
date_from | Дата начала выборки, формат "Y-m-d"
date_to | Дата конца выборки, формат "Y-m-d"
per_page | Количество чеков на одной странице. По умолчанию принимает 100, максимальное значение — 1000.
page | Номер страницы, по умолчанию принимает 1

### Параметры ответа transactions.getTransactions

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
table_id | Id стола
spot_id | Id заведения
client_id | Id клиента
sum | Общая сумма чека
payed_sum | Общая сумма оплаты, от `payed_cash` и `payed_card`
payed_cash | Сумма оплаты наличным расчётом
payed_card | Сумма оплаты безналичным расчётом
payed_cert | Сумма оплаты сертификатом
payed_bonus | Сумма оплаты бонусами
round_sum | Сумма округления по чеку в гривнах или рублях
payed_third_party | Сумма оплаты третьей стороной в копейках
pay_type | Тип оплаты: 0 — закрыт без оплаты, 1 — оплата наличным расчётом, 2 — оплата безналичным расчётом, 3 — смешанная оплата
reason | Причина закрытия чека без оплаты: 1 — гость ушел, 2 — за счёт заведения, 3 — ошибка официанта
tip_sum | Сумма процента за обслуживание
bonus | Начисленный бонус, в процентах от `payed_sum`
discount | Скидка на чек в процентах
print_fiscal | Признак печати фискального чека: 0 — не печатали, 1 — печатали, 2 — фискальный возврат
date_close | Дата закрытия чека, формат "Y-m-d H:i:s"
products | Товары в чеке

Внутри параметра `products` лежит массив, в каждом элементе которого есть следующие параметры:

Параметр | Описание
-------- | --------
product_id | Id товара
modification_id | Id модификации
type | Тип товара: 2 — тех. карта, 3 — товар
workshop_id | Id цеха
num | Количество товара в чеке
product_sum | Стоимость товара
payed_sum | Сумма оплаты
cert_sum | Сумма оплаты сертификатом
bonus_sum | Сумма оплаты бонусами
bonus_accrual | Начислено бонусов
round_sum | Сумма округления по товару
discount | Скидка на товар в процентах
tax_fiscal | Налог по фискальному регистратору
