## incomingOrders.getOwnReservation: Свойства брони со своего приложения

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/incomingOrders.getOwnReservation'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&incoming_order_id=3';

$data = sendRequest($url);

```

> Пример ответа:

```json
{
   "response":{
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
      "address":"московская 9",
      "comment":"Подготовить вазу для цветов",
      "created_at":"2018-03-22 16:50:18",
      "updated_at":"2018-03-22 16:50:18",
      "transaction_id":null,
      "guests_count":"1",
      "duration":"2000",
      "date_reservation":"2018-03-22 18:20:00"
   }
}
```

Метод возвращает свойства брони

### HTTP GET запрос

`GET https://joinposter.com/api/incomingOrders.getOwnReservation`

### GET-параметры запроса incomingOrders.getOwnReservation

Параметр | Описание
-------- | --------
incoming_order_id | Id брони

### Параметры ответа incomingOrders.getOwnReservation

Параметр | Описание
-------- | --------
response | Массив объектов

Внутри параметра `response` лежит объект, внутри которого есть следующие параметры:

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
updated_at | Дата изменения брони
date_reservation | Дата начала брони в формате `Y-m-d H:i:s`
duration | Длительность брони в секундах
