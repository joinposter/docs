## clients.getClientsAccumulations: Накопления клиента по акциям

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/clients.getClientsAccumulations'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Пример ответа:

```json
{  
   "response":[  
      {  
         "accumulation_product_id":"1",
         "tr_product_id":"2125193",
         "promotion_id":"14",
         "client_id":"61",
         "product_id":"934",
         "modification_id":"0",
         "status":"1",
         "num":"1.0000000",
         "product_sum":"1476",
         "prize_product_id":"",
         "date_add":"2018-05-02 13:25:16",
         "date_close":null,
         "weight_flag":"0"
      }
   ]
}
```
 
Метод возвращает накопления клиента по акциям

### HTTP GET запрос

`GET https://joinposter.com/api/clients.getClientsAccumulations`

### GET-параметры запроса clients.getClientsAccumulations

Параметр | Описание
-------- | --------
num | Кол-во клиентов в ответе
offset |  Количество клиентов, которое необходимо пропустить от начала. По умолчанию — 0.

### Параметры ответа clients.getClientsAccumulations

Параметр | Описание
-------- | --------
response | Массив объектов

Внутри параметра `response` лежит массив, в каждом элементе которого есть следующие параметры:

Параметр | Описание
-------- | --------
accumulation_product_id | Id накопления
tr_product_id | Уникальный id товара в рамках всех транзакций
promotion_id | Id акции
client_id | Id клиента
product_id | Id товара
modification_id | Id модификации, если товар с модификациями, 0 — если нет модификации
status | Статус накопления: 1 — активное, 2 — закрыто, 3 — удалено
num | Количество выданного товара
product_sum | Стоимость одного купленного товара 
prize_product_id | Id бонусного товара
date_add | Дата начала накопления в формате `YYYY-MM-dd HH:mm:ss`
date_close | Дата окончания накопления в формате `YYYY-MM-dd HH:mm:ss`
weight_flag | Обозначение весового товара: 0 — товар не весовой, 1 — товар весовой
