## incomingOrders.getIncomingOrder: Свойства онлайн-заказа

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/incomingOrders.getIncomingOrder'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&incoming_order_id=1';

$data = sendRequest($url);
```

> Пример ответа:

```json
{  
  "response":{  
    "incoming_order_id":1,
    "spot_id":1,
    "status":1,
    "client_id":0,
    "first_name":"Антон",
    "last_name":"Талышкин",
    "phone":"79630313844",
    "email":"contact@joinposter.com",
    "sex":1,
    "birthday":"1986-11-23",
    "address":"ул. Малышева, 3",
    "comment":"",
    "created_at":"2017-10-26 14:58:02",
    "updated_at":"2017-10-26 15:25:17",
    "transaction_id":1949,
    "products":[  
      {  
        "io_product_id":1,
        "product_id":113,
        "modificator_id":null,
        "incoming_order_id":1,
        "count":1,
        "created_at":"2017-10-26 14:58:02"
      }
    ]
  }
}
```

Метод возвращает свойства онлайн-заказа

### HTTP GET запрос

`https://joinposter.com/api/incomingOrders.getIncomingOrder`

### GET-параметры запроса incomingOrders.getIncomingOrder

Параметр | Описание
-------- | --------
incoming_order_id | Id онлайн-заказа

### Параметры ответа incomingOrders.getIncomingOrder

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит объект, внутри которого есть следующие параметры:

Параметр | Описание
-------- | --------
incoming_order_id | Id онлайн-заказа
spot_id | Id заведения
status | Статус заказа: 0 — новый, 1 — принят, 7 — отменён
client_id | Id клиента
first_name | Имя клиента
last_name | Фамилия клиента
phone | Телефон клиента
email | Эл. почта клиента
sex | Пол клиента: 0 — не указан, 1 — мужской, 2 — женский
birthday | Дата рождения клиента, формат `Y-m-d`
address | Адрес клиента
comment | Комментарий к онлайн-заказу
created_at | Дата создания онлайн-заказа
updated_at | Дата изменения статуса онлайн-заказа
transaction_id | Id связанного чека
products | Список товаров

Внутри параметра `products` лежит массив, в каждом элементе которого есть следующие параметры:

Параметр | Описание
-------- | --------
io_product_id | Id товара в онлайн-заказе
product_id | Id товара
modificator_id | Id модификатора товара
incoming_order_id | Id онлайн-заказа
count | Количество товара в онлайн-заказе
created_at | Дата добавления товара в онлайн-заказ
