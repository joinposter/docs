## incomingOrders.getOwnReservations: Список броней со своего приложения

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/incomingOrders.getOwnReservations'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);

```

> Пример ответа:

```json
{
   "response":[
      {
         "incoming_order_id":"3",
         "spot_id":"1",
         "status":0,
         "client_id":4985,
         "first_name":"Степан",
         "last_name":"Созонов",
         "phone":"380912152764",
         "email":null,
         "sex":"2",
         "birthday":"1996-08-26",
         "address":null,
         "comment":null,
         "created_at":"2018-03-22 16:50:18",
         "updated_at":"2018-03-22 16:50:18",
         "transaction_id":null,
         "guests_count":"1",
         "duration":"2000",
         "date_reservation":"2018-03-22 18:20:00"
      },
      {
         "incoming_order_id":"4",
         "spot_id":"1",
         "status":1,
         "client_id":4985,
         "first_name":"Владимир",
         "last_name":"Иванченко",
         "phone":"380684111264",
         "email":"vlm.iva@gmail.com",
         "sex":"2",
         "birthday":"1996-08-26",
         "address":"московская 9",
         "comment":"Подготовить вазу для цветов",
         "created_at":"2018-03-22 17:02:41",
         "updated_at":"2018-03-22 17:02:52",
         "transaction_id":"428929",
         "guests_count":"1",
         "duration":"2000",
         "date_reservation":"2018-03-22 18:20:00"
      }
   ]
}
```

Метод возвращает список броней

### HTTP GET запрос

`GET https://joinposter.com/api/incomingOrders.getOwnReservations`

### GET-параметры запроса incomingOrders.getOwnReservations

Параметр | Описание
-------- | --------
status | Фильтр по статусу брони: 0 — новый, 1 — принят, 7 — отменён. По умолчанию не передаётся.
date_from | Дата и время начала выборки, формат `Y-m-d H:i:s`. По умолчанию не передаётся.
date_to | Дата и время конца выборки, формат `Y-m-d H:i:s`. По умолчанию не передаётся.

### Параметры ответа incomingOrders.getOwnReservations

Параметр | Описание
-------- | --------
response | Массив объектов

Внутри параметра `response` лежит массив, в каждом элементе которого есть следующие параметры:

Параметр | Описание
-------- | --------
incoming_order_id | Id брони
type | Тип заказа: 1 — онлайн-заказ, 2 — бронирование. Для этого метода всегда равен 2.
spot_id | Id заведения
status | Статус брони: 0 — новый, 1 — принят, 7 — отменён
client_id | Id клиента
first_name | Имя клиента
last_name | Фамилия клиента
phone | Телефон клиента
email | Эл. почта клиента
sex | Пол клиента: 0 — не указан, 1 — мужской, 2 — женский
birthday | Дата рождения клиента, формат `Y-m-d`
address | Адрес клиента
comment | Комментарий к брони
created_at | Дата создания брони
updated_at | Дата изменения статуса брони
date_reservation | Дата начала брони в формате `Y-m-d H:i:s`
duration | Длительность брони в секундах
